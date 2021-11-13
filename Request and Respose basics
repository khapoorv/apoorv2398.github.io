---
published: false
---
## Requests , Response and Methods


http request : 

url: the method being used  , url , params , http being used  

referer: from where the request originated.

user agent :  tells which browser or client server created the request

host: hostname which is specified bcoz the url does not give the host 

http response : 

http/1.1 200 ok

response first line : http being used , status code and the extra line 

server: tells the web server software 

set cookie : issues a further cookie

pragma : tells the browser to not store cookie in cache 

expire in pragma tells that the cookei expired and to not store hearder in cache

content type is the type of content in body

http methods :


get request  : designed to retieve resources .can be used to send parameter to the request resource

post method is degined to perform actions  and retrieve resources from the browser

can be both get and post method 

head request :  functions the same as get request exept the server should not return message 
body . the server should return the same header as the get request and is used to check if
 the server has the request that is being accessed

trace request : designed for diagnostic . the server should retrun in tthe response body the 
exact content of the request message it recieved . can be used to detect proxy server 

options request :  checks which http methods are available 

put request : attempts to upload the specific resource to the server using the content 
contatined in the body of the request. if the method is available you can add arbitrary script to the
server and execute it .


http headers:

connection  : tells the other end of communication wether it should close the tcp ip  
connection after http transmission has completed or keep it open for further messages

content encoding : specifies what king do encoding is being used for content contained in message 
bod 

content length : indicate lenght of body in head type 

transfer encoding : specifies any encoding that was performed on message body to facilitate its 
transfer over http


Request headers 

accept : tells the server what kinds of content the client is willing to accept such as image types 
ofice document formats and so on 

accept encoding : what type of content encoding the client is wiling to accept 

authorizaion : submits credentials to set server for one of the built in http authenticaion type s

cookie " submits cookie to the server that the server previosuly issued 

host  :  specifies the hostname 

if modified since : speifies when the browser last recieved the requested resource .
if the resource has not changed , since the last time , the server may instruct the client 
to use its cached copy using response with status code 304

if none matched : spefies an entity tag, which is an idnetifer denoting the contents of the 
message body

orgin :  domain from which there quest came

referer specifies the url from which the current request originated.

user agent  :  provides information about the browser or other client software that generated the
request .



Response headers : 

access control allow origin : indicates whether the resource can be retrieved via cross domain ajax request

cache control :  passes caching directives to the browser 

etag : specifies an entity tag 

expires  :  tells the browser forhow ling the contents of the message body are valid . the broser may used cached 
copy of this resource until this time

location : is used in redirection response 

pragma :  passes caching directive to the browser

server :  provides information about the web server software being used . banner grabbing

www- authenticate : is used in response that have a 401 status code to provide details on the type of authentication that the server supports .
______________write here headers _______________

status codes : 
there are 5 types of status codes : 
1xx informational

2xx the request was successful

3xx the client is redirected to a diffrent resource

4xx the request contains an error of some kind 

5xx the server encountered an error fulfilling the request 

all error messages : 

100 continue :  is sent in some circumstance when the client submits a request containing a body
the response indicate that the request headers were recieved and that the client should continue 
sending the body . the server returns a second response when the request has been completed.

200 ok indicates that the request was successful and that the response body contains the 
result of the request .

201 created  : is returned in a response to a put request to indicate that the request was successful 

301 moved permanently :  redirects the browser to a diffrent url which is specified in location header 
the cluent should use the new url future rather than the original 

302 found : redirects the browser temporaryily to a different url ,which is specified
in the location header .

304 not modified : instructs the browser to use its cached copy of the request resource .
the server 

400 bad request : indicates that the client submitted an invalid http request 

401 unauthorized : indicates that the server requires http authenticaion before the request 
will be granted 

403 forbidden : no one is allowed to request resource regardless of authenticaion 

404 not found: indicate that the request resources does not exist 

405 method not allowed : method used in the request is not supported for specified url 

413 request entry too large: body of the request is too large for server to handle 
414 : same as 413

500 internal server error : server encoutered an arror fulfilling the request . INTERNAL SERVER REQUEST


503 service unavilable: the server is functioning but the applicaion accessed via the server 
is not responding 


cookie headers : 


expire : sets when the cookie will expire 

domain: specifies the domain for which the cookie is valid 

path :  specifies the url path for which the cookie is valid 

secure :  the cookie will only be submitted by https request 

httpnly :  the cookie will be accessable byclient side java

same site 


_________________________________________________________________________________________________________________________________

COOKIE WITHOUTsame side ATTRIBUTES
METHODS AND STATUS CODES with correct names


OWASP 
UNVALIDATED REDIRECT AND  mitigation ssrf

USING KNOWN VULNARABLE COMPONENT

VERSION DISCLOSURE
CONCURRENT LOGIN : functionality or risk login on both pc shoudl not happen 
HTTP SECURITY HEADERS

___________________________________________________________________________________________________________________________________


http security headers :

1) X-Frame-Options http headers: is a security header suggested by microsift to avoid the ui redressiong atacks that began with clickjacking 
there are three xframe optiosn : deny |sameorigin | allow from url |

a)deny :  the page must not be embedded into another page within an iframe or any similar html element 
b)sameorigin :  it is paired in terms of secheme , hostname , port 
c)allow from url : the website can only be framed by the url specified here 

instead of content security policy : frame-ancestor  'none' //no url can load the page in an iframe 

content-security polcy frame ancestor  'self ' 

2) x-xss protection http header: reflected xss security filter . filters aim to detect dangerous html input and either prevent the site from 
loading or remove potentially malicious scripts.

x-xss protection 1 : this is the default setting . it enables xss filtering on the web browser and blocks out potential xss payloads from being executed on the page

x-xss protection-1 mode = block :  enables xss filtering in the browser  and avoids execution of x-xss attacks by blocking renedering of the page


3)x-content-type options http header :  used to control the mime type sniffing function in web browser
a) x-content-type-no-sniff : will make sure the browser does not try to sniff the data byte stream 

4) x_download option : no-open  --- ask --- 


5) content security policy headers : vast topic 

prevents aand reduces imact on xss


concurent login :


unvalidated redirect :  unvalidated redirect and forwards happen when the web applicaion accepts untrusted input that could cause the web application to redirect the 
request to a url contatined within untrusted input . by modifying untrused url input to a malicious site .an attacker may launch a phising attacks 


6) http strict transport security http header :

http strict transport security header forces the browser to use a secure web connection . whtih hsts we direct our browser to :
a) convert all request to an https connection 
b) in case of certification related error such as an expired certificate , prevent the user from browsing the sebsite any further 
cache this setting for a specified amount of time . it is defiend for time that is defiend in seconds .
hsts preload list : it is used to prevent mitm attack

additional requirement for the hsts preload list : 
a) you need to serve a valud certifiate
b) you must redirect from http to https on the same host
c) you must support https for all subdomains
d) includesubdomains and preload directives must be specified

7) http public key pinning : website can make their certificate fingerprints known to the browser using the public key pins response header.
browser store these hashes on the user computer. everytime the website is visited , the browser generates a hash based onthe certificate public key . if the hash 
doesnt match the stored vaues the connection wont be established and the incident is reported to a url.
public key pins : sha value , max-age , includeSubdomains,reprot-url.


8) expect ct header : this will eventuall replace hpkp . expect the certificate to be submitted to  certificate transparency log no


a) submission of the certificates to logs ,which is the task of CA

b) montior the logs

c) Auditing , which is doen by built-in auditors in browser

expect ct : enforce , max-age(seconds , reprot-uri = url to which breach report will be sent , enforce: this indicates wether the connection should be established,
if a certificate that doesnt comply with ct is present .


9) refer policy http header :this is used by the owner of the website to know which traffic came from where as the reffere is added in the get request .

referrer type : 

a)""(empty ): this indicates that the referrer-policy is not set and that the directive to control freferer can be set by an html element on the page. this can be done by utilizing<meta>
tag or specifying a policy for inividual html tags using the rel or reffererpolicy atributs 
referre-policy:

b)no-referer: this will not add any referrer header even if the redirected page has the same origin as the host .
referrer-policy : no-referrer

c) no-referrer-when-downgrade : in case of a protocol downgrading (https to http) the referer header will not be sent 

d)same-origin: this only sends the referer header if the targer site is of the same origin 

e)origin :  this truncates the path portion of the url in the referer header. the origin consist of the scheme, domain and port  

f) strict-origin: origin sent only when protocol security is https only.

g) origin when cross-origin : if the target and the host website have the same origin , the referer head wil attak the full url ,else schemen and domain data will
be in header

f) strict-origin-when-cross-origin:same with above with https shaed by same protocol or target site is of higher one

g) unsafe -url :  browsers will share the full url in the referer header in everu request done from the host to the target website . the full url 
will be shared even from unsafe connecitons.


cookie  without same side  attribues : when the cookie does not have same side attributes and becomes vulnarable to attacks 


1) strict: the cookie will not be send alogn with request intiated by third party website 

2) lax :  when you set a cookie samesite attributes to lax the cookie will be sent along with the get request initiated by third party website

3) none cookie will be sent in response to both first party and cross origin request . the cookie attribute secure must be enabled 

 4) http only : prevents javascript from accesing the cookie 

5) expires :  in hwo much time will the cookie expire 

6) max age :  maximum permitted age 

7) path  :  the path that must exist in requested url 

8) secure : cookie is only sent when the server requests with https only .
9) same site : controls wether a cooke is sent with cross site request  . a mitigation for csrf





