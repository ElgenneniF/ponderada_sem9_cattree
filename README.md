# Ponderada Semana 9 - Cattree

## **Pontos de Vulnerabilidade**

Os pontos vulneráveis associados à solução IoT CaTree envolvem a fácil acessibilidade física da entrada do ESP32, que pode ser conectado por qualquer pessoa com um computador e um cabo USB-V8. Ademais, as credenciais do Ubidots não são protegidas, e dependem da consciência dos usuários para criarem senhas fortes ou não compartilharem seus dados com outros. Por fim, vale lembrar que os sensores e microcontroladores podem ter suas funcionalidades alteradas pela presença de sinais eletromagnéticos ou aplicativos de IDEs, tornando o projeto refém do controle interno do IPT sobre cuidados com a solução.

## **Descrição dos Ataques Mapeados**

*Phishing* - Um agente mal intencionado, fingindo ser membro do grupo CaTree pode entrar em contato com os usuários do sistema solicitando as credenciais Ubidots. A partir disso, ele tem acesso aos dados referentes ao Compressor Schulz do IPT. 

*Ameaça Interna* - Um funcionário do IPT pode conectar seu computador fisicamente ao ESP32 da solução IoT e alterar o código como forma de prejudicar as leituras ou roubar credenciais dos demais funcionários imprimindo essas informações no Monitor Serial. 

*Man-in-the-Middle* - Ocorre quando um invasor intercepta a comunicação entre dois dispositivos que acreditam estar se comunicando diretamente e de forma segura. No caso de dispositivos IoT, como no exemplo com o Ubidots, os dados trafegam entre o dispositivo IoT (ESP32) e o servidor da plataforma, podendo incluir informações críticas como leituras de sensores (temperatura e vibração), comandos de controle ou autenticações.

*Ataque DoS* - Ocorre quando um sistema é sobrecarregado intencionalmente com um volume muito grande de solicitações, fazendo com que ele fique indisponível para usuários legítimos. No contexto de IoT, o DoS pode explorar limitações de hardware, software ou rede. –Andre Prado

*Força bruta* - Um ataque de força bruta consiste em uma tentativa de violar uma senha ou um nome de usuário usando uma abordagem de tentativa e erro. Hipotetizando um caso onde a senha de wifi do IPT é simples, comum, ela ser uma senha fraca e fácil de ser quebrada. Dessa forma, um hacker poderia ter contato com o nome da rede que é utilizada no IPT, estando lá perto, por exemplo, assim conseguiria começar a tentativa de entrena nessa rede. Ademais, ele conseguiria tentar quebrar a senha por tentativa e erro, na força bruta, e eventualmente ela poderia ser quebrada, ja que é fraca. - Igor Sguissardi

*Ataque de malware* - Se houverem outros dispositivos no laboratório que estejam comprometidos, um malware pode se espalhar, infectando o nosso dispositivo IoT. Assim,  pode incluir captura de dados ou destruição intencional do sistema.

*Ataque de Perturbação Eletromagnética (EMI)* - Geração intencional de sinais eletromagnéticos para interferir no funcionamento de sensores ou dispositivos eletrônicos, resultando em leituras incorretas, falhas no sistema ou interrupção da comunicação. - Carol Pascarelli

*Ataque de Falsificação de Requisição entre Sites (CSRF)* - O invasor pode induzir um usuário autorizado a executar uma ação maliciosa sem seu consentimento, como alterar configurações da conta na Ubidots ou modificar permissões de dispositivos. Por exemplo, um e-mail contendo um link malicioso pode disparar uma requisição para excluir um dispositivo registrado.
 
*Ataque de Exploração de Firmware* - Um invasor pode explorar vulnerabilidades no firmware do ESP32, utilizando exploits para assumir controle total do dispositivo. Isso pode incluir alterar a programação do dispositivo, desabilitar sensores ou enviar dados falsos para a Ubidots.

*Cavalo de Troia* - Um aplicativo aparentemente legítimo usado para monitorar ou configurar o ESP32 pode conter um Cavalo de Troia. Ao ser executado, ele pode capturar credenciais do sistema, manipular dados do dispositivo ou instalar backdoors para acesso remoto não autorizado.

## **Tabela de Nível de Risco e Impacto Associado**

| **Ataque** | **Nível de Impacto** | **Nível de Risco** |
|----------|----------|----------|
| Phishing | Médio | Baixo |
| Ameaça Interna | Alto | Baixo |
| Man-in-the-Middle | Alto | Baixo | 
| Ataque DoS | Médio - Alto | Baixo |
| Ataque de malware |Médio | Médio |
| Ataque de Perturbação Eletromagnética (EMI) | Médio | Baixo |
| Falsificação de Requisição entre Sites (CSRF)|Alto |Médio |
| Força Bruta | Alto | Alto |
|Exploração de Firmware|Crítico |Alto |
| Cavalo de Troia | Crítico | Alto |


## **Tabela de Contribuições Individuais**

| **Nome** | **Parte** |
|----------|----------|
| Andre | DoS | 
| Carol |Ataque de Malwere| 
| Felipe | Apresentação e EMI |
| Fernanda | Pontos vulneráveis, Phising e Ameaça Interna | 
| Igor | Força Bruta | 
| Lucca |Man-in-the-Middle| 
| Raul | CSRF, Exploração de Firmwere e Cavalo de Troia |
