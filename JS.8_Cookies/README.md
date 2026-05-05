# Manipulação de cookies
## O que é um cookie?
Um cookie é um pequeno arquivo de texto que um site armazena no computador do usuário para guardar informações sobre a sessão do utilizador, preferências, ou outras informações relevantes para a interação do com o site.<br>
Os cookies são amplamente utilizados para melhorar a experiência do utilizador, personalizar conteúdo e rastrear o comportamento do utilizador em um site.<br>
Os cookies servem para persistir informações entre sessões, ou seja, as informações armazenadas no cookie mantêm-se quando o browser é fechado epodem ser recuperadas na próxima vez que o utilizador visitar o site.<br>
Também podem ser utilizadas transmitir informação entre páginas do mesmo site, na mesma sessão ou em sessões posteriores<br>
<br>
O cookie é escrito na sessão contendo vários elementos:
 - nome: serve de identificador e chave de identificação 
 - valor:	o cookie propriamente dito
 - validade: define o tempo máximo que o computador retem o cookie
 - opções:	vários parametros de especificação do cookie, que podem ser desde definições de segurança ao local onde o browser deve armazenar o cookie
  
**Cada cookie tem apenas um valor, mas uma página pode guardar inumeros cookies, tantos quantos os valores a reter**										

## Ambiente de cookies
Ao contrário do armazenamento local - LocalStorage trabalhados em aula anterior - os cookies são enviados para o servidor a cada pedido, o que pode ter um impacto significativo no desempenho, especialmente se os cookies forem grandes ou se houver muitos cookies, mas também requere uma ambiente de operação seguro.<br> 
Em particular, o código tem que ser executados num servidor, mesmo que seja um servidor local, e não diretamente no browsera partir de um arquivo local.<br>
É mais correcto utilizar um servidro funcional - e.g. Apache, Nginx, etc. - ou um emulado - e.g. XAMPP - do que um servidor de desenvolvimento - e.g. Live Server, etc. - mas, para teste podem-se utilizar servidores temporários - e.g. Python HTTP Server - que são fáceis de configurar e usar.	<br>
ex.: 
```
python -m http.server 8080
```
```
http://localhost:8080/1.JSSetCookie.htm
```
**NOTAS**: 
- O número da porta (8080) pode ser outro, desde que esteja livre
- O comando python tem que ser executado na pasta onde estão os ficheiros HTML e JS ou tem que se adapatar o caminho para os ficheiros HTML e JS
- O servidor tem que ser reiniciado sempre que se fizer alterações nos ficheiros HTML e JS, para que as alterações sejam refletidas no browser.

## Cookies vs. LocalStorage
| Cookies | LocalStorage |
| --- | --- |
| Enviado para o servidor a cada pedido | Processado apenas no lado do cliente  |
| Limite de armazenamento de cerca de 4KB por cookie | Limite de armazenamento de cerca de 5MB por domínio |
| Pode ser configurado para expirar após um certo tempo | Não tem expiração, permanece até ser explicitamente removido |
| Pode ser configurado para ser acessível apenas por HTTP (HttpOnly) | Acessível apenas por JavaScript |
| Pode ser configurado para ser transmitido apenas em conexões seguras (Secure) | Não aplicável (sendo local...) |
| Pode ser acedido por subdomínios, dependendo da configuração do domínio | Acessível apenas no domínio que o criou |
| Pode ser lido em qualquer página do mesmo domínio | Acessível apenas na página que o criou, a menos que seja compartilhado entre páginas do mesmo domínio |

## Cookies e segurança
Os cookies podem ser usados para armazenar informações sensíveis, como credenciais de login (**muito desaconselhado**), preferências do utilizador, ou outras informações pessoais. <br>
Por outro lado, os cookies são ficheiros de texto armazenados no computador do utilizador, o que significa que podem ser lidos e modificados por qualquer pessoa com acesso ao computador. <br>
Por isso, é importante tomar medidas de segurança para proteger os cookies contra acesso não autorizado e ataques maliciosos. Algumas práticas recomendadas incluem:
- Usar a ***flag HttpOnly*** para impedir que os cookies sejam acessíveis por JavaScript, o que pode ajudar a prevenir ataques de cross-site scripting (XSS).
- Usar a ***flag Secure*** para garantir que os cookies sejam transmitidos apenas em conexões seguras (HTTPS), o que pode ajudar a prevenir ataques de ***man-in-the-middle*** (MITM).
- Configurar a política de ***SameSite*** para controlar o envio de cookies em solicitações cross-site, o que pode ajudar a prevenir ataques de ***cross-site request forgery*** (CSRF).
- Evitar armazenar informações sensíveis em cookies, ou usar criptografia para proteger os dados armazenados em cookies.
- Limitar a validade dos cookies para reduzir o risco de exposição de informações sensíveis em caso de comprometimento do cookie.