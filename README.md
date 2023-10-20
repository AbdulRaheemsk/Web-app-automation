# Web-app-automation
package Assignment;

import static org.junit.Assert.*;
import java.util.List;
import org.junit.AfterClass;
import org.junit.Before;
import org.junit.Test;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.support.ui.Select;

import dev.failsafe.internal.util.Assert;
import selenium.webDriver;

public class Assigntest {
	static WebDriver driver;
	

	@AfterClass
	public static void tearDownAfterClass() throws Exception {
		
	}

	@Before
	public void setUp() throws Exception {
		driver = new ChromeDriver();
		String baseUrl = "https://www.trukky.com/door-to-door-goods-delivery";
		driver.get(baseUrl);
		System.out.println(baseUrl);
	}

	@Test
	public void test() throws InterruptedException {
		driver.manage().window().maximize();
        String title=driver.getTitle();
        System.out.println("Title is "+ title);
        
        Thread.sleep(15000);

        
    WebElement from = driver.findElement(By.xpath("//*[@id=\"__next\"]/div/main/div/div/form/div/div[1]/input"));
        from.sendKeys("Hyderabad, Telangana, India");
        from.click();
        
           WebElement pickup = driver.findElement(By.xpath("//*[@id=\"__next\"]/div/main/div/div/form/div/div[1]/div/ul/li[1]/div/span[2]"));
           pickup.click();
        		   
        
        WebElement To= driver.findElement(By.xpath("//*[@id=\"__next\"]/div/main/div/div/form/div/div[2]/input"));
       To.sendKeys("New Delhi, Delhi, India");
       To.click();
       
       WebElement drop = driver.findElement(By.xpath("//*[@id=\"__next\"]/div/main/div/div/form/div/div[2]/div/ul/li[1]/div/span[2]"));
       drop.click();
     
       WebElement CheckPrice = driver.findElement(By.xpath("//*[@id=\"__next\"]/div/main/div/div/form/button"));
       CheckPrice.click();
       
       Thread.sleep(3000);
       
       WebElement Servicetype =driver.findElement(By.xpath("//*[@id=\"__next\"]/div/main/div/ul/li[2]/div"));
       Servicetype.click();
       
       Thread.sleep(3000);
       
       WebElement Loadtype = driver.findElement(By.xpath("//*[@id=\"__next\"]/div/main/div/ul/li[1]/div"));
       Loadtype.click();
       
       Thread.sleep(3000);
       
       WebElement Material = driver.findElement(By.xpath("//*[@id=\"__next\"]/div/main/div[1]/div/div[1]"));
       Material.click();
       
       Thread.sleep(3000);
       
       Select dropdown=new Select (driver.findElement(By.xpath("//*[@id=\"form_0\"]/div[1]/div[2]/select")));
       dropdown.selectByVisibleText("Window AC");
       
       Thread.sleep(2000);
       
      WebElement Items = driver.findElement(By.xpath("//*[@id=\"form_0\"]/div[2]/div/div[2]/input"));
      Items.sendKeys("2");
      
      
      driver.findElement(By.xpath("//*[@id=\"form_0\"]/div[3]/button")).click();
       
      driver.findElement(By.xpath("//*[@id=\"__next\"]/div/main/div[2]/button")).click();
      
      Thread.sleep(2000);
      
      String month = "April 2024";
      String date = "28";
      
      while(true) {
    	String text=driver.findElement(By.xpath("//*[@id=\"__next\"]/div/main/div[1]/div/div/div[1]/button[3]/span")).getText();
    	if(text.equals(month)) {
    		  break;
    	}
    	else {
   		  driver.findElement(By.xpath("//*[@id=\"__next\"]/div/main/div[1]/div/div/div[1]/button[4]")).click();
    	}
    	}
      driver.findElement(By.xpath("//*[@id=\"__next\"]/div/main/div[1]/div/div/div[2]/div/div/div/div[2]/button[29]/abbr")).click();
    	
   Thread.sleep(2000);
      
      WebElement Next = driver.findElement(By.xpath("//*[@id=\"__next\"]/div/main/div[2]/button"));
      Next.click();
      
      Thread.sleep(2000);
      
      WebElement Number = driver.findElement(By.xpath("//*[@id=\"__next\"]/div/main/div[1]/form/div/input"));
      Number.sendKeys("1234567890");
      
      
      driver.findElement(By.xpath("//*[@id=\"__next\"]/div/main/div[2]/button")).click();
      
	}
	

	}
