# Computer Science

## 2026/05/18
https://www.digitalocean.com/community/tutorials/multithreading-in-java#frequently-asked-questions-faqs
In Java, when you run a program, the Java Virtual Machine (JVM) starts a process. Inside that process, the JVM can run multiple threads to perform different tasks.


Threads within the same process share memory and resources, enabling faster communication.
Context switching can occur between threads to allow multiple tasks to execute efficiently.
Process is the Independent program with its own memory
Thread is small unit of a process sharing same memory
Use ExecutorService: The ExecutorService framework in Java provides a high-level API to manage thread pools and execute tasks asynchronously. This is recommended for managing a large number of threads.

synchronized 
Multithreading is a core concept in Java that allows multiple threads to run concurrently, maximizing CPU utilization and making applications more efficient. Java provides built-in support for multithreading, making it a critical topic for developers.
<img width="750" height="321" alt="image" src="https://github.com/user-attachments/assets/8d9ba4a0-3981-46cd-a9ed-a9ec89015851" />

Java thread states include NEW, RUNNABLE, BLOCKED, WAITING, TIMED_WAITING, and TERMINATED.
Calling start() twice on the same thread results in IllegalThreadStateException. A thread can only be started once.


The sleep(1000) method pauses thread execution for 1 second (1000 milliseconds). The thread then moves back to RUNNABLE.
join()
A thread is the smallest unit of execution within a program, allowing multiple tasks to run concurrently. In Java, threads help improve performance by enabling parallel execution.


Note: The order of thread execution may vary on each run because thread scheduling is non-deterministic.


Concurrency
<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/adb3689e-f4bf-49bf-a369-07ee370bff1a" />

## 2026/05/14
An atomic operation is a type of operation that runs without interruption, ensuring that it is completed as a single, indivisible unit. These operations are commonly used in computer science for tasks like updating counters and are implemented using processor atomic instructions to prevent interruptions and maintain data integrity.


<img width="686" height="386" alt="image" src="https://github.com/user-attachments/assets/032ec06f-b459-4c40-9c57-f76d2c4c8e00" />

Los tres mecanismos clave de la solución son:
1. beginTransaction() — agrupa todas las operaciones en una unidad atómica. Si algo falla, todo se deshace.
2. SELECT ... FOR UPDATE — esta es la pieza fundamental. Le dice a MySQL que bloquee la fila del usuario hasta que la transacción termine. Cualquier otro proceso que intente acceder a esa misma fila queda en cola, no puede leer ni escribir hasta que se libere el candado.
3. UPDATE saldo = saldo - ? — en lugar de leer el saldo en PHP y restarlo ahí, la operación matemática ocurre directamente en la base de datos, eliminando la ventana de vulnerabilidad entre lectura y escritura.
Otras estrategias complementarias que puedes combinar:

Rate limiting por usuario — limitar a una solicitud de retiro por segundo por cuenta desde el backend o un proxy como Nginx.
Cola de trabajo — procesar retiros secuencialmente con una queue (Redis + workers), evitando concurrencia desde la raíz.
Optimistic locking — agregar una columna version a la tabla: si al hacer UPDATE la versión ya cambió, se reintenta. Útil cuando los conflictos son raros y no quieres bloquear lecturas.
Para comprobar esto, se pueden utilizar varias herramientas. En este caso se utilizará el software Burpsuite, que mediante una extensión (Turbo Intruder) puede ejecutar múltiples solicitudes HTTP de forma simultánea. 
Python tiene una función de bloqueo incorporada para el acceso a los recursos llamada threading.Lock.

Si agregas las funciones lock.acquire y lock.release logras bloquear el acceso al recurso para que ningún otro hilo acceda a ese recurso al mismo tiempo.
Esta extensión realizará 100 solicitudes simultáneas y todas retirarán $10.000 (el dinero total de la cuenta).

Una vez ejecutado el programa, podemos ver que 9 solicitudes retiraron $10.000. Esto quiere decir que retiramos $90.000 de una cuenta con solo $10.000.
A modo de prueba de concepto, levantamos un servidor basado en el pseudo-código para emular el caso en un exchange de crypto.

Si ingresamos la cantidad de dinero a retirar y presionamos el botón RETIRAR, la aplicación eliminará ese monto del total asociado a la cuenta. 
Interferencia de un proceso no confiable: el atacante inserta un fragmento de código entre los pasos de un proceso seguro.
Interferencia de un proceso confiable: el atacante explota dos procesos diferentes que comparten algún estado en común.
Sin los controles adecuados, los diferentes procesos pueden interferir entre sí. Cuando el tiempo de algunas acciones impacta en otras, los eventos pueden ocurrir fuera de secuencia, lo que resulta en un comportamiento anómalo. Este comportamiento anómalo es una Race Condition.
¿Qué es una Race Condition?
Race Condition es una vulnerabilidad que ocurre cuando un sistema que maneja tareas en una secuencia específica es forzado a realizar dos o más operaciones simultáneamente. 

Esto permite que los atacantes tomen ventaja del intervalo de tiempo que se da entre el inicio de un servicio y el momento en que un control de seguridad surte efecto. 

Con las Race Condition los atacantes pueden acceder a recursos compartidos como bases de datos, archivos y objetos en código para modificarlos simultáneamente y/o afectar la integridad del recurso.
## 2026/05/13
JWT header signature carne JPA Repository
## 2026/05/12
Runners
A runner is a server that runs your workflows when they're triggered. Each runner can run a single job at a time. GitHub provides Ubuntu Linux, Microsoft Windows, and macOS runners to run your workflows. Each workflow run executes in a fresh, newly-provisioned virtual machine.
Actions
An action is a pre-defined, reusable set of jobs or code that performs specific tasks within a workflow, reducing the amount of repetitive code you write in your workflow files. Actions can perform tasks such as:

Pulling your Git repository from GitHub
Setting up the correct toolchain for your build environment
Setting up authentication to your cloud provider
You can write your own actions, or you can find actions to use in your workflows in the GitHub Marketplace.
You can configure a job's dependencies with other jobs; by default, jobs have no dependencies and run in parallel. When a job takes a dependency on another job, it waits for the dependent job to complete before running.

You can also use a matrix to run the same job multiple times, each with a different combination of variables—like operating systems or language versions.

For example, you might configure multiple build jobs for different architectures without any job dependencies and a packaging job that depends on those builds. The build jobs run in parallel, and once they complete successfully, the packaging job runs.
A job is a set of steps in a workflow that is executed on the same runner. Each step is either a shell script that will be executed, or an action that will be run. Steps are executed in order and are dependent on each other. Since each step is executed on the same runner, you can share data from one step to another. For example, you can have a step that builds your application followed by a step that tests the application that was built.
Events
An event is a specific activity in a repository that triggers a workflow run. For example, an activity can originate from GitHub when someone creates a pull request, opens an issue, or pushes a commit to a repository. You can also trigger a workflow to run on a schedule, by posting to a REST API, or manually.
Electro
You can give the workflow file any name you like, but you must use .yml or .yaml as the file name extension. YAML is a markup language that's commonly used for configuration files.
Workflows
A workflow is a configurable automated process that will run one or more jobs. Workflows are defined by a YAML file checked in to your repository and will run when triggered by an event in your repository, or they can be triggered manually, or at a defined schedule.

Workflows are defined in the .github/workflows directory in a repository. A repository can have multiple workflows, each of which can perform a different set of tasks such as:

Building and testing pull requests
Deploying your application every time a release is created
Adding a label whenever a new issue is opened
## 2026/05/11
Entonces “build” significa:
compilar código (si aplica)
juntar archivos
optimizar
preparar versión final
Continuos Integration Continuos Delivery Deployment

git checkout -b feature/login
git status

The CMD instruction sets the command to be executed when running a container from an image.


RUN <<EOF
apt-get update
apt-get install -y curl
EOF
The RUN instruction will execute any commands to create a new layer on top of the current image. The added layer is used in the next step in the Dockerfile. RUN has two forms:
FROM instructions support variables that are declared by any ARG instructions that occur before the first FROM.
FROM can appear multiple times within a single Dockerfile to create multiple images or use one build stage as a dependency for another. Simply make a note of the last image ID output by the commit before each new FROM instruction. Each FROM instruction clears any state created by previous instructions
Shell and exec form
The RUN, CMD, and ENTRYPOINT instructions all have two possible forms:

INSTRUCTION ["executable","param1","param2"] (exec form)
INSTRUCTION command param1 param2 (shell form)
FROM busybox
ENV FOO=/bar
WORKDIR ${FOO}   # WORKDIR /bar
ADD . $FOO       # ADD . /bar
COPY \$FOO /quux # COPY $FOO /quux
docker compose watch
Docker runs instructions in a Dockerfile in order. A Dockerfile must begin with a FROM instruction. This may be after parser directives, comments, and globally scoped ARGs. The FROM instruction specifies the base image from which you are building. FROM may only be preceded by one or more ARG instructions, which declare arguments that are used in FROM lines in the Dockerfile.
Environment replacement
Environment variables (declared with the ENV statement) can also be used in certain instructions as variables to be interpreted by the Dockerfile. Escapes are also handled for including variable-like syntax into a statement literally.
Use root/example as user/password credentials

services:

  db:
    image: mysql
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: example
    # (this is just an example, not intended to be a production configuration)

docker run -t -d 8080:80 docker/todo-app
## 2026/05/08
@Transient le dice a JPA que ignore ese campo — no crea columna ni lo incluye en queries. Final no funciona igual. Es un caso muy común con campos calculados o de presentación.
 @Transactional funciona vía proxy AOP — Spring envuelve tu bean en un proxy que intercepta llamadas externas. Un método privado o una llamada desde dentro de la misma clase no pasa por el proxy. Bug muy real.
 @RestController combina @Controller + @ResponseBody, serializando automáticamente la respuesta a JSON. @Controller solo devuelve nombres de vistas. Si usaste Thymeleaf alguna vez, lo sabes.
 N+1 es el problema más común con JPA. 1 query para las órdenes + N queries para los productos de cada una. Se resuelve con JOIN FETCH o @EntityGraph. Cualquiera con un año real lo habrá sufrido.
Con inyección por campo no puedes instanciar la clase en un test sin Spring. Con constructor, pasas las dependencias directo en el new. Es un punto que solo conoces si escribiste tests reales.
✅ Las tres registran un bean en el contexto de Spring, pero @Repository añade traducción automática de excepciones de BD a DataAccessException. Quien tiene un año real lo sabe.
El problema N+1 en JPA — nadie lo estudia, lo sufres en producción
Los proxies AOP de @Transactional — el bug del método privado decepciona a muchos en su primer año
@Autowired en campo vs constructor — solo lo cuestionas cuando empiezas a escribir tests unitarios
docker push sube la imagen al registro. Antes necesitas hacer docker login y haber tageado la imagen como miusuario/mi-app:latest con docker tag.
Los contenedores son efímeros por diseño. Para persistir datos usas volúmenes (docker volume) o bind mounts, que viven fuera del contenedor.
 docker rm $(docker ps -aq) elimina todos los contenedores (el flag -a = todos, -q = solo IDs). También puedes usar docker container prune.
docker-compose te permite definir y arrancar varios contenedores (app + base de datos + cache, etc.) con un solo archivo y un solo comando.
Correcto ✅ docker logs nombre-o-id muestra la salida estándar del contenedor. Útil agregar -f para seguir los logs en tiempo real (como tail -f).
docker exec -it abc123 bash. docker run crearía un contenedor nuevo. exec ejecuta un comando en uno que ya existe.
El Dockerfile es la receta de tu imagen: define desde qué base partes, qué instalas, qué archivos copias y qué comando ejecuta al arrancar.
docker build -t nombre:tag ruta. El punto (.) indica que el Dockerfile está en el directorio actual. El flag -t asigna nombre y tag.
Exacto ✅ Una imagen es como un molde o plantilla — incluye el sistema base, dependencias y tu app. A partir de ella puedes crear múltiples contenedores.
The given Docker command "docker push user_name/repository_name" is used to push changes done in a Docker image into Docker Hub.
he given Docker command "docker commit -m “My first update” container_ID user_name/repository_name" is used to commit changes done in a Docker image. This command creates a new image from the changes made in a container. The -m flag is used to add a commit message to describe the changes made. T
A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image. It is used to automate the creation of Docker images by specifying the base image, adding dependencies, and configuring the environment. 
Containers running on a single machine share the same operating system kernel, which allows them to start instantly and use RAM more efficiently. This is because containers do not require a separate operating system instance for each container, unlike virtual machines. Instead, they utilize the host machine's operating system, resulting in faster startup times and optimized resource utilization. Therefore, the statement is true.
Namespaces make the isolation of the process that runs a Docker container possible.
Containers are a lightweight form of virtualization that includes the application and all its dependencies. They operate in isolation from other containers and run as isolated processes in userspace on the host operating system. 
Control groups are what make it possible to limit the amount of CPU time and memory allocated to a given container.

Security groups are typically associated with AWS configurations, and Kubernetes is a container orchestration tool.
Es una plantilla que contiene todo lo necesario para ejecutar una aplicación, incluyendo el código fuente, las dependencias y las configuraciones.
Contenedor Docker
¿Cuál es el comando para descargar una imagen de Docker desde el repositorio público de Docker Hub?
Docker will pull the image from Docker Hub.
Docker containers are less resource intensive, as they provide process-level virtualization as opposed to full OS virtualization provided by a VM, which is one of the reasons the industry has shifted toward containers.
¿Qué comando se utiliza para iniciar un contenedor de Docker?

¿Cuál es el comando para listar todos los contenedores activos en un host Docker?
docker stop
Kubernetes is an orchestration tool that manages Docker deployments, but it is not a Docker alternative. LXD, rkt and the Windows Server Containers are container implementation technologies that compete with Docker.



## 2026/05/07
The assertIterableEquals() method in JUnit 5 is used to assert that two iterables contain the same elements in the same order. It compares the elements of the iterables one by one.
Q. What is the purpose of the @DisabledOnOs annotation in JUnit 5?
wer. The @TestInstance annotation in JUnit 5 controls the lifecycle of test instances. It can be used to specify whether a new instance should be created for each test method (PER_METHOD) or a single instance should be used for all methods in the test class (PER_CLASS).
The correct answer is B. @Priority is not a valid order annotation for test method execution in JUnit 5. The correct annotations are @Order (for individual methods), @TestMethodOrder (for specifying the ordering strategy for a class), and @OrderWith (for custom MethodOrderer implementations).
Wrong answer. The correct answer is A. The assertSame() method in JUnit 5 is used to verify that two objects refer to the same object. It checks if the two object references point to the same memory location.
A. Dynamic Tests in JUnit 5 allow you to dynamically generate test cases at runtime. They are created by factory methods annotated with @TestFactory and can generate a stream, collection, or iterable of DynamicTest instances.
 B. The @ExtendWith annotation in JUnit 5 is used to add custom extensions to a test class or method. It allows you to register extension classes that can modify or enhance the behavior of tests.
is C. assumeNotNull() is not a valid assumption method in JUnit 5. The valid assumption methods are assumeTrue(), assumeFalse(), and assumingThat(). Assumptions are used to run tests only if certain conditions are met.
B. The @Timeout annotation in JUnit 5 is used to set a time limit for test execution. If the test doesn't complete within the specified time, it fails with a TimeoutException.
@TestMethodOrder
Correct answer. The @Nested annotation in JUnit 5 is used to define inner test classes. It allows you to create a hierarchical structure of tests, grouping related tests together and potentially sharing setup code.
he assertEquals(double expected, double actual, double delta) method in JUnit is used to compare floating-point numbers with a delta for precision. The delta parameter allows for a small difference between the expected and actual values to account for floating-point imprecision.
@RepeatedTest
The @RepeatedTest annotation in JUnit 5 is used to run a test method multiple times. It allows you to specify the number of repetitions for a test, which can be useful for testing consistency or performance.
assertAll() @TempDir
B. JUnit 5 uses the concept of Extensions to allow users to extend the framework with custom behavior. Extensions can be used to add custom lifecycle callbacks, parameter resolution, test instance post-processing, and more.
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
