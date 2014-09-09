/* Throwing and catching IOException */

import java.io.*;

public class Catcher{


	public static void main(String[] args) throws IOException{
		System.out.println("Boo!");
		
		Catcher c = new Catcher();
		c.doCatcher();
	}
	public void doCatcher() throws IOException{
		FileReader freader = null;
	try{
		char[] data = new char[100];
		File file = new File("file.txt");
		freader = new FileReader(file);
		int size = freader.read(data);
		System.out.print(size + " ");
		for (char c : data){
			System.out.print(c);
		}
	}catch(FileNotFoundException fnfe){
		System.out.println("Uh-oh, FNFE strikes again!");
	}
	finally{	
	//	if(freader != null) 
		try{
			freader.close();
		}catch(NullPointerException npe){
			System.out.println("Phew!");
		}
	}
	}
}
