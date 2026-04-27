# Computer Science
## 2026/04/27
⚠️ 2. N+1 problem
🧠 Qué es

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
