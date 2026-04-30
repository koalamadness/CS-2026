# Computer Science
## 2026/04/30
    <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter-engine</artifactId>
            <version>6.0.3</version>
            <scope>test</scope>
        </dependency>
import org.junit.jupiter.api.Test;

import static org.junit.jupiter.api.Assertions.assertEquals;

public class CalculatorTest {

    @Test
    public void addTest() {


        Calculator calculator = new Calculator();
        int result = calculator.add(10, 20);

        assertEquals(30, result);

    }


}

<img width="541" height="576" alt="image" src="https://github.com/user-attachments/assets/0ff34359-b313-4124-95cb-a0e347e0571f" />

<img width="1267" height="605" alt="image" src="https://github.com/user-attachments/assets/191f4e4a-d7af-4dd8-92df-f2753afd2810" />

<img width="1258" height="579" alt="image" src="https://github.com/user-attachments/assets/6219a181-c5fe-4127-9ca2-e2136f38172a" />

## 2026/04/29
assertNotNull
GIVEN
WHEN THEN
Nested
Vocabulary
@ExtendWith(MockitoExtension.class)
    @DisplayName("Create ")
   @Test
    @Disabled
    void ignore() {
        
    }
## 2026/04/28
Cuéntame cómo pruebas una funcionalidad nueva desde cero
¿Qué debe llevar un buen reporte de bug?
¿Te ha pasado que algo funciona en tu entorno pero falla en producción? ¿Qué hiciste?
¿Qué lenguaje conoces y para qué lo has usado?
¿Has usado herramientas como Postman? ¿Para qué?
Si una API te regresa datos incorrectos, ¿cómo validarías dónde está el problema?
¿Qué haces si encuentras muchos errores pero te piden liberar rápido?
En un login, ¿qué probarías?
En un formulario, ¿qué validarías sí o sí?
Si un botón no responde, ¿qué revisarías antes de reportarlo?
¿Cómo te comunicas con desarrolladores cuando algo no está bien?
¿Prefieres trabajar con instrucciones claras o explorar por tu cuenta?
¿Te funciona un esquema híbrido?
Dockerfile
https://www.youtube.com/watch?v=Geq60OVyBPg
## 2026/04/27
vale, pude contestar todas jsata un tercio de senior , por ejemplo, no se Retries, circuit breakers, timeouts, fallback y observabilidad.
⚠️ 2. N+1 problem
🧠 Qué es
🧩 1. ORM
🧠 Qué es

ORM (Object-Relational Mapping) es una forma de trabajar con bases de datos usando objetos en vez de SQL directo.

En Spring Data JPA el ORM más común es Hibernate.
Es un problema de rendimiento donde haces 1 query principal + N queries adicionales innecesarias.
Kids
<img width="665" height="727" alt="image" src="https://github.com/user-attachments/assets/4dea0cf2-b385-43f6-a5f9-7338d07cdd7b" />
@Test
void shouldReturnPokemonFromApi() {
    PokemonApi api = mock(PokemonApi.class);
    when(api.getPokemon("pikachu")).thenReturn(new Pokemon("pikachu"));

    PokemonService service = new PokemonService(api);

    Pokemon result = service.getPokemon("pikachu");

    assertEquals("pikachu", result.getName());
}
## 2026/04/23
git hub actions blame
event job explore 1 vivo per lei
## 2026/04/22
Dockerfile
Docker 
Image
Container
## 2026/04/21
netstat
Lambda
AIM
DynamDB
API Gateway
Amplify
## 2026/04/20
pipe | >
cat
bucket instance rdbs expot enviroment variables npm start allow all IPS region & disown ELB CLOUDFRINT
route 53
CDN
grep
## 2026/04/17
laggiu
## 2026/04/16
API 
REST
Docker
subnet
routing
segmentation
## 2026/04/15
BackUp EC2 ISNTANCE AIM S3 RBDS
## 2026/04/13
BackUp
## 2026/04/14
EC2 S3 
