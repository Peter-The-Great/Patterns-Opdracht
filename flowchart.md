```mermaid
classDiagram
    Bank <|.. ING
    Bank <|.. ABNAMRO
    Bank <|.. Rabobank
    Loan <|.. HomeLoan
    Loan <|.. BussinessLoan
    Loan <|.. EducationLoan
    AbstractFactory <|.. BankFactory
    AbstractFactory <|.. LoanFactory
    class Bank{
        + getBankName(): String
    }
    class ING{
        - bankName: String
        + getBankName(): String
    }
    class ABNAMRO{
        - bankName: String
        + getBankName(): String
    }
    class Rabobank{
        - bankName: String
        + getBankName(): String
    }

    class Loan{
        <<Abstract>>
        + calculateLoanPayment(loanAmount: double, years: int): void
    }
    class HomeLoan{
        + calculateLoanPayment(loanAmount: double, years: int): void
    }
    class BussinessLoan{
        + calculateLoanPayment(double: loanamount, int: years): void
    }
    class EducationLoan{
        + calculateLoanPayment(loanAmount: double, years: int): void
    }
    class AbstractFactory{
        <<Abstract>>
        + getBank(String bank): Bank
        + getLoan(String loan): Loan
    }
    class BankFactory{
        + getBank(String bank): Bank
        + getLoan(String loan): Loan
    }
    class LoanFactory{
        + getBank(String bank): Bank
        + getLoan(String loan): Loan
    }
    class FactoryCreator{
        + getFactory(String choice): AbstractFactory
    }
```