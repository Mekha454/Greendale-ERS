# Greendale-ERS
The Expense Reimbursement System (ERS) will manage the process of reimbursing employees for expenses incurred while on company time.  All employees in the company can log in and submit requests for reimbursements and view their past tickets and pending requests. Managers can log in and view all reimbursement requests and past history for all employees in the company. Managers are authorized to approve and deny requests for expense reimbursements.

# Models

**Employee**

The Employee model contains user information

     {
       Id: number, // serial, primary key
       firstName: string, // not null
       lastName: string, // not null
       department: string, // not null
     }


**Login**

The Login model stores user credentials and access

    {
      username: string, // primary key
      password: string, // not null
      isManager: boolean, // not null
    }

**Request**

The Request model represents a single reimbursement submitted by an Employee

    {
      id: number, // primary key
      employee: string, // not null
      amount: number, // not null
      reason: string, // not null
      date: date, // not null
      status: string, // not null
      approvedBy: string, // not null
     }
 
# Endpoints
 
 **Login**
 
  ● URL: /user/login
  
  ● Method: `POST`
  
  ● Request: 
  
    {
      username: string,
      password: string,
    } 
   
   ● Response:
   
    Employee
  
 **Find All Requests**
 
  ● URL: `/request/all`
  
  ● Method: `GET`
  
  ● Allowed: Manager
  
  ● Response:
  
    [Request]
    
    
 **Submit New Request**
 
  ● URL: `/request/new`
  
  ● Method: `POST`
  
  ● Request:
  
    Request
    
  ● Response:
  
    Request
