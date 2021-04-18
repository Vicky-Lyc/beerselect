POM.XML
<?xml version="1.0" encoding="UTF-8"?>
<web-app version="2.5" xmlns="http://java.sun.com/xml/ns/javaee"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://java.sun.com/xml/ns/javaee
	http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd">
    <servlet>
        <description>BeerSelect</description>
        <display-name>BeerSelect</display-name>
        <servlet-name>BeerSelect</servlet-name>
        <servlet-class>com.example.web.BeerSelect</servlet-class>
    </servlet>
    <servlet-mapping>
        <servlet-name>BeerSelect</servlet-name>
        <url-pattern>/SelectBeer.do</url-pattern>
    </servlet-mapping>
    <welcome-file-list>
        <welcome-file>form.html</welcome-file>
    </welcome-file-list>
</web-app>

beerselect.java
package com.example.demo4;
import java.io.IOException;
import java.io.PrintWriter;
import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
public class beerselect extends HttpServlet {
    public beerselect() {
        super();
        System.out.println("in Constructor of BeerSelect.");
    }
    public void destroy() {
        super.destroy();
        System.out.println("in destroy of Constructor.");
    }
    public void doPost(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        System.out.println("int doPost of Constructor.");
        response.setContentType("text/html");
        PrintWriter out = response.getWriter();
        out.print("beer selection advice<br>");
        String color = request.getParameter("color");
        out.print("got beer color : " + color);
    }

    public void init() throws ServletException {
        // Put your code here
        System.out.println("in init of Constructor.");
    }
}

index.jsp
<%@ page contentType="text/html; charset=UTF-8" pageEncoding="UTF-8" %>
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN">
<html>
<head>
    <title>beerselect.html</title>
    <meta http-equiv="keywords" content="keyword1,keyword2,keyword3">
    <meta http-equiv="description" content="this is my page">
    <meta http-equiv="content-type" content="text/html; charset=UTF-8">

</head>
<body>
<h1>
    beer selection page
</h1>
<br>
<form method="post" action="SelectBeer.do" name="beerForm">
    <p>
        select beer characteristics
    </p>
    <p>
        <select name="color" size="1">
            <option value="1">
                light
            </option>
            <option value="2">
                amber
            </option>
            <option value="3">
                brown
            </option>
            <option value="4">
                dark
            </option>
        </select>
    </p>
    <p>
        <input type="submit" value="submit" name="submit">
    </p>
    <p>
         
    </p>
    <p>
         
    </p>
    <p>
         
    </p>
</form>
</body>
</html>
