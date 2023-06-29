# flow-project1
This is a simple contract which allows you to register students by providing their details such as first name, last name, registration number, current semester, and  address. The student information is stored in a mapping, where the key is the student's address, and the value is a Student object containing the provided details.

# Program Execution
In this project I have created a smart contract named StudentRegistration and deployed it.In that I created a dictionary name students that maps an address type to student type.This mapping will store the information of each student registered in the contract.

    pub var students: {Address: Student}


Inside the contract, I created a struct called Student that represents the details of a student. It has the following properties:

firstName: A string representing the first name of the student.
lastName: A string representing the last name of the student.
registration_no: A string representing the registration number of the student.
semester: A string representing the current semester of the student.
account: An Address representing the address associated with the student.
The Student struct also has an initializer (init function) that takes in the aforementioned properties as arguments and initializes the struct.

 pub struct Student {
        pub let firstName: String
        pub let lastName: String
        pub let registration_no: String
        pub let semester: String
        pub let account: Address

        // You have to pass in 4 arguments when creating this Struct.
        init(_firstName: String, _lastName: String, _registration_no: String,_semester:String, _account: Address) {
            self.firstName = _firstName
            self.lastName = _lastName
            self.registration_no = _registration_no
            self.semester = _semester
            self.account = _account
        }
    }


    The contract includes a public function named addStudent. This function allows you to add a new student to the students mapping. It takes the following arguments:

firstName: A string representing the first name of the student to be added.
lastName: A string representing the last name of the student to be added.
registration_no: A string representing the registration number of the student to be added.
semester: A string representing the current semester of the student to be added.
account: An Address representing the address associated with the student to be added.
Inside the addStudent function, a new Student object is created using the provided arguments. The Student struct's initializer is called with the arguments, and the resulting object is assigned to the newStudent variable. Then, this new student object is added to the students mapping, using the student's address (account) as the key.


    pub fun addStudent(firstName: String, lastName: String,registration_no: String,semester:String, account: Address)
    {
        let newStudent = Student(_firstName: firstName, _lastName: lastName, _registration_no:registration_no,_semester:semester,_account: account)
        self.students[account] = newStudent
    }

   init() 
     {
            self.students = {}
     }
The contract's init function is the constructor that initializes the students mapping as an empty mapping. It is called when the contract is deployed.
     
    

# authors
ISHIKA ANASANE
