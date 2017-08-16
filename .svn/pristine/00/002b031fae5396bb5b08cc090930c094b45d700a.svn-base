package egovframework.example.welcomeWeb.web;

import java.util.Enumeration;
import java.util.List;
import java.util.Map;

import javax.annotation.Resource;
import javax.servlet.http.HttpServletRequest;

import org.springframework.stereotype.Controller;
import org.springframework.ui.ModelMap;
import org.springframework.web.bind.annotation.RequestMapping;

import egovframework.example.welcomeWeb.service.WelcomeWebService;

@Controller
public class WelcomeWebController {

	@Resource(name = "welcomeWebService")
	private WelcomeWebService welcomeWebService;
	
	@SuppressWarnings({ "rawtypes" })
	@RequestMapping(value = "/welcomeWeb.do")
	public String welcomeWeb(HttpServletRequest request, ModelMap model) throws Exception {
		
		List<Map> welcomeWebList = welcomeWebService.selectWelcomeWebServiceList();
		
		List<Map> pieChartList = welcomeWebService.selectPieChartList();
		
		model.addAttribute("welcomeWebList", 	welcomeWebList);
		model.addAttribute("pieChartList", 		pieChartList);
		
		return "welcomeWeb/welcomeWeb.tiles";
	}
	
	@RequestMapping(value = "/eightTest.do")
	public String welcomeWebCheck(HttpServletRequest request, ModelMap model) throws Exception {

		/*String arr[] = request.getParameterValues("hanq");
		
		if(arr != null) 
		{
			for (String a : arr)
			{
				System.out.println(a);
			}
		}*/
		
		List<Map> welcomeWebList = welcomeWebService.selectWelcomeWebServiceList();
		
		List<Map> pieChartList = welcomeWebService.selectPieChartList();
		
		Enumeration<String> attr = request.getParameterNames();
		
		while(attr.hasMoreElements()) 
		{ 
			String attrName = attr.nextElement(); 
			
			System.out.println(attrName);
			
			if(attrName.equals("hanq")) 
			{
				String[] arr = request.getParameterValues("hanq");
				
				for(String a : arr) 
				{
					System.out.println(a);
				}
				
				model.addAttribute("arr", arr);
			}
		}
		
		model.addAttribute("welcomeWebList", 	welcomeWebList);
		model.addAttribute("pieChartList", 		pieChartList);
		
		return "welcomeWeb/welcomeWeb.tiles";
	}
	
	@RequestMapping(value = "/welcomeWebInclude.do")
	public String welcomeWebInclude(HttpServletRequest request, ModelMap model) throws Exception {
		
		List<Map> welcomeWebList = welcomeWebService.selectWelcomeWebServiceList();
		
		List<Map> pieChartList = welcomeWebService.selectPieChartList();
		
		model.addAttribute("welcomeWebList", 	welcomeWebList);
		model.addAttribute("pieChartList", 		pieChartList);
		
		return "welcomeWeb/welcomeWebInclude.tiles";
	}
}
