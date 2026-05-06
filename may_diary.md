# Computer Science
## 2026/05/06

## 2026/05/05
NullPointerException
    @Test
    public void getStudentByNameAssert() {
        
        StudentService studentService = new StudentService();
        Student student = new Student("Papi", 1);
        studentService.addStudent(student);


        assertThrows(StudentNotFoundException.class, ()-> {
            studentService.getStudentByName("Papi");
        } );
        
    }
        assertEquals(1, actualObject.getId());
public class StudentNotFoundException extends RuntimeException {

    public StudentNotFoundException(String message) {
        super(message);
    }

}

## 2026/05/04
Jobs Event YAML Runners
assertTrue(() -> result);
assertTrue(() -> result, "Denied");
assertFalse(result);
assertNull(actualObject);
    @Test
    public void getStudentByIdTest(){
        StudentService studentService = new StudentService();

        Student student = new Student("Ramesh", 1);
        studentService.addStudent(student);

        Student actualObject = studentService.getStudentById(7);

        assertNull(actualObject);
    }
