# Computer Science
## 2026/05/06
   @Test
    @DisplayName("✅ Suma de dos números positivos")
    public void addTest() {
        Calculator calculator = new Calculator();

        int result = calculator.add(10, 20);

        assertEquals(30, result);
    }
ProveedorÚsalo cuando...@ValueSourceUn solo parámetro simple@CsvSourcePocos casos, múltiples columnas simples@CsvFileSourceMuchos casos o datos externos@MethodSourceNecesitas objetos complejos o lógica para generar datos@EnumSourceQuieres probar todos (o algunos) valores de un Enum
import org.junit.jupiter.params.provider.Arguments;
import java.util.stream.Stream;

@ParameterizedTest
@MethodSource("proveerDatosDeDescuento")
void deberiaAplicarDescuento(double precio, int descuento, double esperado) {
    assertEquals(esperado, calc.aplicarDescuento(precio, descuento));
}

// El método debe ser static y retornar Stream<Arguments>
static Stream<Arguments> proveerDatosDeDescuento() {
    return Stream.of(
        Arguments.of(1000.0, 10, 900.0),
        Arguments.of(500.0,  20, 400.0),
        Arguments.of(200.0,   0, 200.0),
        Arguments.of(100.0, 100,   0.0)
    );
}
@ParameterizedTest
@ValueSource(strings = {"hola", "mundo", "java"})
void stringNoDeberiaEstarVacio(String texto) {
    assertFalse(texto.isEmpty());
}
Patrón AAA: Arrange (preparar), Act (ejecutar), Assert (verificar)
Un test = una responsabilidad → cada test verifica una sola cosa
Nombra con claridad → deberiaRetornarErrorSiEmailEsNulo()
Patrón AAA: Arrange (preparar), Act (ejecutar), Assert (verificar)
Tests independientes → no deben depender entre sí
No lógica compleja en los tests → deben ser simples y legibles
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
