# Computer Science
## 2026/05/06
Patrón AAA: Arrange (preparar), Act (ejecutar), Assert (verificar)

import org.junit.jupiter.params.ParameterizedTest;
import org.junit.jupiter.params.provider.CsvSource;

@ParameterizedTest
@CsvSource({
    "1, 1, 2",
    "5, 3, 8",
    "0, 0, 0"
})
void testSumaParametrizada(int a, int b, int esperado) {
    assertEquals(esperado, calc.sumar(a, b));
}

@TestMarca un método como prueba@BeforeEachSe ejecuta antes de cada prueba@AfterEachSe ejecuta después de cada prueba@BeforeAllSe ejecuta una vez antes de todas las pruebas (debe ser static)@AfterAllSe ejecuta una vez después de todas las pruebas (debe ser static)@DisabledDeshabilita una prueba@DisplayNameNombre legible para la prueba
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
