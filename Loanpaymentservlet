<!DOCTYPE html>
<html>
<head>
    <title>Loan Payment Calculator</title>
</head>
<body>
    <h1>Loan Payment Calculator</h1>
    <form action="LoanPaymentServlet" method="post">
        <label for="loanAmount">Loan Amount:</label>
        <input type="text" id="loanAmount" name="loanAmount" required><br><br>

        <label for="interestRate">Annual Interest Rate (%):</label>
        <input type="text" id="interestRate" name="interestRate" required><br><br>

        <label for="numberOfYears">Number of Years:</label>
        <input type="text" id="numberOfYears" name="numberOfYears" required><br><br>

        <input type="submit" value="Compute Loan Payment">
    </form>
</body>
</html>


import java.io.IOException;
import java.io.PrintWriter;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

@WebServlet("/LoanPaymentServlet")
public class LoanPaymentServlet extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        response.setContentType("text/html");
        PrintWriter out = response.getWriter();

        // Retrieve user input from the form
        double loanAmount = Double.parseDouble(request.getParameter("loanAmount"));
        double annualInterestRate = Double.parseDouble(request.getParameter("interestRate"));
        int numberOfYears = Integer.parseInt(request.getParameter("numberOfYears"));

        // Calculate monthly and total loan payments using the Loan class
        Loan loan = new Loan(annualInterestRate, numberOfYears, loanAmount);
        double monthlyPayment = loan.getMonthlyPayment();
        double totalPayment = loan.getTotalPayment();

        // Display the results
        out.println("<html><head><title>Loan Payment Result</title></head><body>");
        out.println("<h1>Loan Payment Result</h1>");
        out.println("<p>Loan Amount: $" + loanAmount + "</p>");
        out.println("<p>Annual Interest Rate: " + annualInterestRate + "%</p>");
        out.println("<p>Number of Years: " + numberOfYears + "</p>");
        out.println("<p>Monthly Payment: $" + monthlyPayment + "</p>");
        out.println("<p>Total Payment: $" + totalPayment + "</p>");
        out.println("</body></html>");
    }
}
