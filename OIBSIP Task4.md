# OIBSIP
Oasis Infobyte Java Development Internship Tasks. # Task4


//                                                     :::TASK 4:::
// **************************************************ONLINE EXAMINATION*****************************************************



    import java.util.*;
	public class task4 {
	Scanner scobj = new Scanner(System.in);
	HashMap<String,Integer> Details = new HashMap<String,Integer>();
	    public void User_Login() {
			Details.put("Dipak",9876);
			System.out.println("\n------ WELCOME TO THE ONLINE EXAMINATION------");
			String Uname;
			System.out.println("Enter UserName : ");
			Uname = scobj.next();
			int PWD;
			System.out.println("Enter Password : ");
			PWD= scobj.nextInt();
			if(Details.containsKey(Uname)) {
				if(Details.get(Uname)==PWD){
					System.out.println("\nWelcome");
					Options_Menu();	}
				else {
					System.out.println("Enter Valid Password For: "+Uname);
					User_Login();    }
	        }
			else{
				System.out.println("Enter Valid User Name");
			}
	    
		}
		public void Options_Menu() {
			int Choice;
			System.out.println("===User Menu===");
			System.out.println("1.Update The Profile \n2.Write Exam \n3.Quit ");
			System.out.println("Enter The Choice: ");
			Choice = scobj.nextInt();
			switch(Choice) {
			case 1:
				Details=Update_Details();
				Options_Menu();
				break;
			case 2:
				Examination();
				Options_Menu();
				break;
			case 3:
	            System.out.println("Thank You");
				System.exit(0);
				break;
			default:
				System.out.println("Please Enter Number in User Menu Only");
			}
		}
		public HashMap<String,Integer> Update_Details(){
			String update_name;
			int update_pwd;
			System.out.println("updateDetails Profile");
			System.out.println("Enter The Username: ");
			update_name = scobj.next();
			if(Details.containsKey(update_name)) {
			System.out.println("Enter The New Password ");
			update_pwd = scobj.nextInt();
			Details.replace(update_name, update_pwd);
	        System.out.println("Successfully Updated Your Details");
			}
			else {
				System.out.println("Enter The Correct UserName");
			}
			return Details;
		}
	public void Examination() {
	    Calendar cr = Calendar.getInstance();
		long StartTime=System.currentTimeMillis();
		long EndTime=StartTime+30;
		int AnsweredQueries=0;
		int UserAnswer,MarksSecured;
		System.out.println("Please Start Your Exam");
		System.out.println("Examination Instructions: ");
		System.out.println("You Have To Answer 5 Questions in 30 Seconds");
		System.out.println("Each Question carries 10 marks and -5 for wrong answer");
		HashMap<String,ArrayList<String>> queries=new HashMap<String,ArrayList<String>>();
		ArrayList<String> Ques1=new ArrayList<String>();
	    Ques1.add("JVM");
		Ques1.add("JRE");
		Ques1.add("JDK");
		Ques1.add("JDB");
		Ques1.add("4");
		queries.put("____ is used to find and fix bugs in the Java programs",Ques1);
		ArrayList<String> Ques2=new ArrayList<String>();
		Ques2.add("0 to 256");
		Ques2.add("-128 to 127");
		Ques2.add("0 to 65535");
		Ques2.add("none");
		Ques2.add("3");
		queries.put("what is the numerical range of a char datatype in java?",Ques2);
		ArrayList<String> Ques3=new ArrayList<String>();
		Ques3.add("0");
		Ques3.add("Not a number");
		Ques3.add("Infinity");
		Ques3.add("none");
		Ques3.add("3");
		queries.put("What does the expression float a = 35 / 0 return?",Ques3);
		ArrayList<String> Ques4=new ArrayList<String>();
		Ques4.add("Polymorphism");
		Ques4.add("Inheritance");
		Ques4.add("compilation");
		Ques4.add("Encapsulation");
		Ques4.add("3");
		queries.put("which of the following is not an OOPS concept in java?",Ques4);
	    ArrayList<String> Ques5=new ArrayList<String>();
		Ques5.add(".js");
		Ques5.add(".txt");
		Ques5.add(".class");
		Ques5.add(".java");
		Ques5.add("4");
		queries.put("what is the extension of java code files?",Ques5);
		int sno=0;
	    Set<String> set=queries.keySet(); 
	    ArrayList<String> al=new ArrayList<>(set);
	    int x=al.size();
		while(System.currentTimeMillis()<EndTime || sno<x) {
	        String i=al.get(sno);
			System.out.println("\n\nQ."+(sno+1)+") "+i);
			System.out.println("\n(1) "+queries.get(i).get(0)+"\t"+"(2) "+queries.get(i).get(1)+"\t"+"(3) "+queries.get(i).get(2)+"\t"+"(4) "+queries.get(i).get(3)+" ");
			System.out.println("Enter Option");
			UserAnswer=scobj.nextInt();
			System.out.println("Your Answers Are Submited.....");
			if(UserAnswer==Integer.parseInt(queries.get(i).get(4))) {
				AnsweredQueries++;
			}
	        sno++;
		}
		System.out.println("You Have Completed the Exam");
		MarksSecured=AnsweredQueries*10-((5-AnsweredQueries)*5); 
		System.out.println("Your score is..."+" "+MarksSecured+"/50");	
	}

	public static void main(String[] args)
	{
		task4 em =new task4();
			em.User_Login(); 
	}
	}
