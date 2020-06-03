import java.util.Scanner;
public class Main {
  public static void main(String[] args) {
    Scanner cin=new Scanner(System.in);
    int n=2,m=1,a=5;
    String [] candidate=new String[n];
    int [] vote=new int [n];
    for(int i=0;i<n;i++){
      candidate[i]=cin.nextLine();
    }
    int p=cin.nextInt();
    String [] voter=new String[p];
    voter[0]=cin.nextLine(); //剛用完nextInt不能接著用nextLine
    for(int i=0;i<p;i++){
      voter[i]=cin.nextLine();
      check(voter[i],vote,m);
    }
    for(int i=0;i<n;i++){
      System.out.println(candidate[i]+" "+vote[i]);
    }
  }
  static void check(String str,int [] vote,int m){
    int i,j=0;
    for(i=0;i<str.length();i++){
      if(str.charAt(i)=='0'){ 
        continue;
      }
      else  
        if(str.charAt(i)=='*' && m>0){
          m--;
        } 
        else{
	  	    return;
	      } 
    }
    into(str,vote);
  }  
  static void into(String str,int [] vote){
    for(int i=0;i<str.length();i++){
      if(str.charAt(i)=='*'){
        vote[i]++;
      }
    }
  }
