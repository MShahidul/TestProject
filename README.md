# TestProject
Test Project for Interview proecss 

package com.omgeo;



import org.openqa.selenium.By;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;

public class VerifyAboutPage {

	/**
	 * 
	 * @ Shahidul Islam
	 *  Verify about page title
	 */
	public static void main(String[] args)  {
		
		WebDriver driver= new FirefoxDriver();
		
		driver.get("http://www.omgeo.com");
	    
		//driver.wait(500);
		
		driver.findElement(By.xpath("html/body/div[1]/div[1]/div[2]/div[2]/ul/li[1]/a")).click();
		
		System.out.println(driver.getTitle());
		//driver.wait(500);
		String Text=driver.findElement(By.cssSelector("span.HeroHeaderOrange")).getText();
		
		assertTrue("Text is not right, Expected:'What We Bring to the Table',Actual:"
		
				+Text,
						Text.equalsIgnoreCase("What We Bring to the Table"));	
	 
		driver.quit();
	
	}

	
	
	
	private static void assertTrue(String string, boolean equalsIgnoreCase) {
		
		
	}}






package com.omgeo;

import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.firefox.FirefoxDriver;

public class FindProductNameFromDropDown {

	/**
	 * @Shahidul Islam
	 * 
	 * verify Alert page from  drop down field
	 */
	public static void main(String[] args) {
		
		WebDriver driver= new FirefoxDriver();
		
		driver.get("http://www.omgeo.com");
	    
		//driver.wait(500);
		
		driver.findElement(By.xpath("html/body/div[1]/div[1]/div[2]/div[2]/ul/li[1]/a")).click();
		
		driver.findElement(By.xpath("html/body/div[1]/div[2]/table/tbody/tr[1]/td[2]/table/tbody/tr[2]/td[2]/div/div/a/div/b")).click();
		
		List<WebElement> dropDown=driver.findElements(By.xpath("html/body/div[1]/div[2]/table/tbody/tr[1]/td[2]/table/tbody/tr[2]/td[2]/div/div/div/ul/li"));
		
		int total_node=dropDown.size();
		
		for(int i=0;i< total_node;i++){
		
			String alert=dropDown.get(i).getText();
			
			if(alert.equalsIgnoreCase("Alert"))
			{
				dropDown.get(i).click();
	
		String Text=driver.findElement(By.cssSelector("span.HeroHeaderPink")).getText();
				
		assertTrue("Text is not right, Expected:'Omgeo ALERT',Actual:"
				
						+Text,
								Text.equalsIgnoreCase("Omgeo ALERT"));	
			 
				driver.quit();
			
			}
		}
	}

	private static void assertTrue(String string, boolean equalsIgnoreCase) {

		
	}

}



package com.omgeo;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;

public class VerifyTextFromLeadershipPage {

	/**
	 * @ Shahidul Islam
	 * 
	 * 
	 */
	public static void main(String[] args) {
		WebDriver driver= new FirefoxDriver();
		
		driver.get("http://www.omgeo.com");
	   	
		driver.findElement(By.xpath("html/body/div[1]/div[1]/div[2]/div[2]/ul/li[1]/a")).click();
		
		driver.findElement(By.xpath("html/body/div[1]/div[1]/div[2]/div[2]/div[2]/ul/li[2]/a")).click();
		
		driver.findElement(By.xpath("html/body/div[1]/div[2]/table/tbody/tr[2]/td/span[2]/a")).click();
		
		driver.quit();

	}

}

	
