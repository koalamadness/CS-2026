# Computer Science
## 2026/05/07
Correct answer. The assertAll() method in JUnit 5 is used to combine multiple assertions into a single statement. It allows you to group related assertions and see all failures at once, rather than stopping at the first failure.


Correct answer. In JUnit 5, the @Disabled annotation is used to disable a test method or class. Tests marked with @Disabled will not be executed by the test runner.
Correct answer. The assertThrows() method in JUnit is used to verify that a specific piece of code throws an expected exception. It allows you to test exception handling in your code.
Correct answer. JUnit test methods can be public void methods. They do not need to return a value or have parameters, and they should not be private to allow the JUnit runner to execute them.

Correct answer. The @ParameterizedTest annotation in JUnit 5 is used to run a test multiple times with different parameters. It allows you to define a set of inputs and expected outputs for a single test method.
Correct answer. The @TempDir annotation in JUnit 5 is used to create a temporary directory for file operations during tests. It provides a clean, isolated file system location for each test, which is automatically cleaned up after the test.





Correct answer. The @Test annotation is used to mark a method as a test in JUnit 5. Methods annotated with @Test will be executed as test cases by the JUnit runner.
## 2026/05/06
Testcontainers levanta una BD real dentro de Docker
automáticamente solo para tus tests ✅
    @Test
    @DisplayName("Remover last Operation reduce el espacio")
    void removerOperacion() {

        List<String> historial = repository.obtenerHistorial();

        service.add(1, 1);
        service.add(5, 5);
        service.divide(10, 2);

        int beforeRemoveSize = repository.totalOperaciones();

        service.removeLastOperation();

        int afterRemoveSize = repository.totalOperaciones();

        assertEquals(beforeRemoveSize - 1, afterRemoveSize);

    }
    @Test
    @DisplayName("División por cero NO debería guardarse en el historial")
    void divisionPorCeroNoDeberiaGuardarseEnHistorial() {
        // Act & Assert — lanza excepción
        assertThrows(ArithmeticException.class,
                () -> service.divide(10, 0)
        );

        // El historial debe estar vacío — no se guardó nada
        assertEquals(0, repository.totalOperaciones());
    }
    @ParameterizedTest(name = "✅ {0} + 1 debería ser {0} + 1")
    @ValueSource(ints = {1, 5, 10, 100, -5, 0})
    @DisplayName("Sumar cualquier número con 0 retorna el mismo número")
    void addUno(int num) {
        int result = calculator.add(num, 1);
        assertEquals(num + 1, result);
    }

    @BeforeAll
    static void antesTodo() {
        System.out.println("🚀 Iniciando suite de pruebas de Calculator...");
    }

    @BeforeEach
    void setup() {
        System.out.println("🔧 Creando nueva instancia de Calculator...");
        calculator = new Calculator();
    }
   @AfterEach
    void tearDown() {
        System.out.println("🧹 Limpiando después del test...");
        calculator = null;
    }

    @AfterAll
    static void afterAll() {
        System.out.println("✅ Suite de pruebas finalizada.");
    }
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
