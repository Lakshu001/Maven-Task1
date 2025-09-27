**#1**
package Sel1;

import org.openqa.selenium.firefox.FirefoxDriver;

public class WebBrowser {

	public static void main (String[] args) {
		

		FirefoxDriver driver = new FirefoxDriver();

		driver.get("https://www.google.co.in/");
		driver.manage().window().maximize();
		String d = driver.getTitle();
		
		System.out.println("Page Titile : " + d);
		
		String refreshedTitle = driver.getTitle();
		
		System.out.println("After Refersh  : " + refreshedTitle);
	
		driver.quit();
	}
}



**#2**
package Sel1;

import org.openqa.selenium.chrome.ChromeDriver;

public class Demo1 {

	public static void main (String[] args) {
		
		ChromeDriver driver = new ChromeDriver();
		
		driver.get("https://WWW.demoblaze.com/");
		driver.manage().window().maximize();
		String d =  driver.getTitle();
		
		System.out.println("Page Title : " + d );
		
		if (d.equals("STORE")) {
			
			System.out.print("Page landed on correct website");
		}else {
		System.out.println("page not landed correct website");	
		}
		
	}
}



**#3**
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import io.github.bonigarcia.wdm.WebDriverManager;

public class Wiki1{
	
	public static void main (String[] args) throws InterruptedException {
		
		WebDriverManager.chromedriver().setup();
		WebDriver w = new ChromeDriver();
		
		w.manage().window().maximize();
		w.get("https://www.wikipedia.org/");
		WebElement searchBox = w.findElement(By.id	("searchInput"));
		searchBox.sendKeys("Artificial intelligence");
		searchBox.submit();
		
		Thread.sleep(1000);
		WebElement historyLink = w.findElement(By.xpath("//a[@href='#History']"));
		historyLink.click();
	    
		Thread.sleep(5000);
		WebElement historySelectionTitle = w.findElement(By.xpath("//span[text()='History']\r\n" + ""));
		System.out.println("Title of selection : " + historySelectionTitle.getText());
		
	} 
	
}
