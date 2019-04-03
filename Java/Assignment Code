import java.util.Comparator;
import java.util.PriorityQueue;
import java.util.Scanner;

public class UpGrad {       //done by Clay Motupalli clay.motupalli2017@vitstudent.ac.in

    private static final int MAX=100;
    private static PriorityQueue<Student> pq;
    private static String cmd;

    public static void main(String[] args){

         pq = new PriorityQueue<>(MAX, new StudentComparator());
        Scanner sc = new Scanner(System.in).useDelimiter("\n");

        int n=sc.nextInt(); //number of commands

        for(int i=0;i<n;i++){
            //command line interface here
            cmd=sc.next();
            if(cmd.contains("ENTER")){

                String details=cmd.substring(6);
                String name=details.substring(0,details.indexOf(' '));
                String cgpa=details.substring(details.indexOf(' ')+1,details.lastIndexOf(' '));
                String token=details.substring(details.lastIndexOf(' ')+1);

                Student s=new Student(name,Double.parseDouble(cgpa),Integer.parseInt(token));
                pq.add(s); //enqueuing a student


            }
            else if(cmd.contains("SERVED")){
                pq.poll();    //dequeuing the student
            }
        }
        display();

    }


    public static void display(){
        if(pq.isEmpty()){
            System.out.println("EMPTY");
            return;
        }

        while (!pq.isEmpty()) {
            System.out.println(pq.poll().getName());
        }
    }
}

class StudentComparator implements Comparator<Student> {  //custom Comparator

    public int compare(Student s1, Student s2) {
        if (s1.getCgpa() < s2.getCgpa())
            return 1;
        else if (s1.getCgpa() > s2.getCgpa())
            return -1;

        if(!s1.getName().equals(s2.getName()))
            return s1.getName().compareTo(s2.getName());


         if (s1.getToken() < s2.getToken())
            return 1;
        else if (s1.getToken() > s2.getToken())
            return -1; //here return which token is greater

        return  0;
    }
}

class Student {
    private String name;
    private double cgpa;
    private int token;

    public Student(String name, double cgpa, int token) {

        this.name = name;
        this.cgpa = cgpa;
        this.token=token;
    }

    public String getName() {
        return name;
    }

    public double getCgpa() {
        return cgpa;
    }

    public int getToken() {
        return token;
    }
}

