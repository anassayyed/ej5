index.html <html> 
<head> 
<title>Calculator</title> 
</head> 
<body> 
<form action="Calculator"> 
 Enter First Number <input type="text" name="txtN1"><br> 
 Enter Second Number <input type="text" name="txtN2"><br> 
 Select an Operation<br> 
<input type="radio" name="opr" value="+">ADDITION<br> 
<input type="radio" name="opr" value="-">SUBTRACTION<br> 
<input type="radio" name="opr" value="*">MULTIPLY<br> 
<input type="radio" name="opr" value="/">DIVIDE <br> 
<input type="reset"><br> 
<input type="submit" value="Calculate"> 
</form> 
</body> 
</html> 
 
 
Java Code: 
Calculator.java Package mypack; import java.io.IOException; import java.io.PrintWriter; import javax.servlet.ServletException; import javax.servlet.http.HttpServlet; import javax.servlet.http.HttpServletRequest; import javax.servlet.http.HttpServletResponse; public class NewServlet extends HttpServlet { 
public void doGet(HttpServletRequest request, HttpServletResponse response) 
 throws ServletException, IOException { 
 response.setContentType("text/html;charset=UTF-8"); 
 PrintWriter out = response.getWriter(); 
 
out.println("<html><head><title>Calculator</title></head><body>"); double n1 = Double.parseDouble(request.getParameter("txtN1")); double n2 = Double.parseDouble(request.getParameter("txtN2")); double result =0; 
 String opr=request.getParameter("opr");  if(opr.equals("+"))      result=n1+n2;  
 if(opr.equals("-"))      result=n1-n2;  if(opr.equals("*"))      result=n1*n2;   if(opr.equals("/"))      result=n1/n2;  out.println("<h1> Result = "+result);  out.println("</body></html>"); 
} 
 } 
