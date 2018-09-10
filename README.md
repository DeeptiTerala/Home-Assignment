    
      package hometask;

import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class HomeTask {
	
		
	public static void main(String args[])
	{
		 System.setProperty("webdriver.chrome.driver","C:\\Users\\Cherry\\Downloads\\chromedriver_win32\\chromedriver.exe");
		 WebDriver driver = new ChromeDriver();  //ChromeDriver Object is been created
		 driver.manage().window().maximize();
		 driver.get("https://www.ss.com/en ");   // URL has been passed
		 driver.manage().timeouts().implicitlyWait(50,TimeUnit.SECONDS);		 
		 driver.findElement(By.xpath("//*[@id=\"main_table\"]/span[2]/b[3]/a")).click(); // Finding Search option in main menu
		 driver.findElement(By.id("ptxt")).sendKeys("Clothes");  //Entering Text in the Search Field
		 driver.manage().timeouts().implicitlyWait(200,TimeUnit.SECONDS);
		 driver.findElement(By.xpath("//*[@id=\"sbtn\"]")).sendKeys(Keys.ENTER);
		
		try {
		 driver.findElement(By.name("mid[]")).click();	
				 
	     driver.findElement(By.className("d1")).click();
	     driver.findElement(By.id("a_fav")).click();
	     System.out.println("Added to favourites");
	     
		 driver.findElement(By.xpath("//*[@id=\"main_table\"]/span[2]/span/b/a")).click();
		 System.out.println("Successfully Added to memo");
		}
		
	   catch (Exception e)
	   {
	   System.out.println("No Results found in Search criteria ");	
	   }
	   }
	
	
	}	 
    
    
