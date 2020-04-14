package EnnymaxQA.EnnymaxQA;

import java.net.HttpURLConnection;
import java.net.URL;
import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class BrokenLinks
{
	public static void main(String[] args) throws Exception
	{
		// TODO Auto-generated method stub
		System.setProperty("webdriver.chrome.driver", "C:\\Users\\CONFIRMZ\\eclipse-workspace\\EnnymaxQA\\target\\chromedriver.exe");
		WebDriver driver = new ChromeDriver();
		driver.get("https://www.azeezco.ng");
		
		Thread.sleep(5000);
		
		// this section deals with finding broken links
		
		List<WebElement> links = (List<WebElement>) driver.findElements(By.xpath("//*[@id=\"month\"]"));
				//driver.findElement(By.xpath("/html/body/main/div/div/form"));
		System.out.println(links.size());
		
		for (int i=0; i<links.size(); i++)
		{
		WebElement element = links.get(i);
		String url = element.getAttribute("href");
		URL link = new URL(url);
		HttpURLConnection httpConn = (HttpURLConnection) link.openConnection();
		Thread.sleep(2000);
		httpConn.connect();
		int re_code = httpConn.getResponseCode();
		if(re_code>=400)
		{
			System.out.println(url + "-" + "is broken");
		}
		else
		{
			System.out.println(url + "-" + "is valid");
		}
		}
		
		driver.quit();

	}

}
