<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8" %>
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Addition Quiz</title>
</head>
<body>
    <h1>Addition Quiz</h1>
    
    <form action="quiz.jsp" method="post">
        <%
            // Generate two random numbers for the addition quiz
            int num1 = (int)(Math.random() * 100);
            int num2 = (int)(Math.random() * 100);
            
            // Calculate the correct answer
            int correctAnswer = num1 + num2;
            
            // Retrieve the user's answer (if submitted)
            String userAnswerStr = request.getParameter("userAnswer");
            int userAnswer = -1; // Default value
            
            // Check if the user has submitted an answer
            if (userAnswerStr != null && !userAnswerStr.isEmpty()) {
                userAnswer = Integer.parseInt(userAnswerStr);
            }
            
            // Check if the user's answer is correct
            boolean isCorrect = (userAnswer == correctAnswer);
        %>
        
        <p><%= num1 %> + <%= num2 %> = <input type="text" name="userAnswer" size="5"></p>
        
        <input type="hidden" name="correctAnswer" value="<%= correctAnswer %>">
        
        <p><input type="submit" value="Submit Answer"></p>
    </form>
    
    <%
        // Display the result if the user has submitted an answer
        if (userAnswerStr != null && !userAnswerStr.isEmpty()) {
    %>
    <h2>Result:</h2>
    <p>Your answer: <%= userAnswer %></p>
    <p>Correct answer: <%= correctAnswer %></p>
    <p><%= (isCorrect ? "Correct" : "Incorrect") %></p>
    <%
        }
    %>
</body>
</html>
