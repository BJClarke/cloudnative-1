---

copyright:
  years: 2017
lastupdated: "2017-06-12"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}

# Fehlerbehebung
{: #ts}

Manche bekannte Probleme mit dem {{site.data.keyword.dev_cli_notm}} sind zusammen mit den entsprechenden Problemumgehungen dokumentiert.
{:shortdesc}

<!-- Add a headings and paragraphs about troubleshooting for your service, or a list of known issues and workarounds. -->

## Bekannte Probleme
{: #knownissues}

In den folgenden Abschnitten werden bekannte Probleme und mögliche Lösungen beschrieben.


### Fehler im Hostnamen beim Erstellen eines Projekts mit nicht mobilem Muster
{: #hostname}

Es wird der folgende Fehler angezeigt, wenn Sie mit dem {{site.data.keyword.dev_cli_short}} unter Verwendung von Web-App-, BFF- oder Microservice-Mustern ein Projekt erstellen:

```
The hostname <myHostname> is taken.
```
{: codeblock}


#### Ursache
{: #hostname-cause}
   
Dieser Fehler tritt aufgrund einer abgelaufenen Anmeldung auf.


#### Lösung
{: #hostname-resolution}

Erneute Anmeldung.

```
bx login
```
{: codeblock}


### Allgemeine Fehler mit dem {{site.data.keyword.dev_cli_short}}
{: #general}

Es wird eventuell der folgende Fehler angezeigt, wenn Sie mit dem {{site.data.keyword.dev_cli_short}} Befehle erstellen, löschen, auflisten oder codieren:

```
Failed to <command> project.
```
{: codeblock}


#### Ursache
{: #general-cause}
   
Dieser Fehler tritt aufgrund einer abgelaufenen Anmeldung auf.


#### Lösung
{: #general-resolution}

Erneute Anmeldung.

```
bx login
```
{: codeblock}


### Fehler: 'No such image' bei Ausführung eines neuen Projekts
{: #nosuchimage}

Es wird eventuell der folgende Fehler angezeigt, wenn Sie ein Projekt ausführen, ohne es vorher erstellt zu haben. 

```
$ bx dev run testProject
The run-cmd option was not specified
Stopping the 'testProject' container...
The 'testProject' container was not found
Creating image bx-dev-testProject based on Dockerfile...
OK
Creating a container named 'testProject' from that image...
FAILED
Container 'testProject' could not be created:
Error: No such image: bx-dev-testProject
```


#### Ursache
{: #nosuchimage-cause}

Sie müssen ein Projekt erstellen, bevor Sie es ausführen.  


#### Lösung
{: #nosuchimage-resolution}

Führen Sie den folgenden Befehl im aktuellen Projektverzeichnis aus, um die Anwendung zu erstellen:

```
bx dev build
```
{: codeblock}

Führen Sie den folgenden Befehl im aktuellen Projektverzeichnis aus, um die Anwendung zu starten:

```
bx dev run
```


### Service-Broker-Fehler beim Hinzufügen der {{site.data.keyword.objectstorageshort}}-Funktion
{: #os}

Es wird eventuell der folgende Fehler angezeigt, wenn Sie das {{site.data.keyword.dev_cli_short}} zum Erstellen von zwei Projekten mit der {{site.data.keyword.objectstorageshort}}-Funktion verwenden.

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}


#### Ursache
{: #os-cause}
   
Dieser Fehler ist auf den {{site.data.keyword.objectstorageshort}}-Service zurückzuführen, der nur eine Instanz des kostenfreien {{site.data.keyword.objectstorageshort}}-Plans bereitstellt. 


#### Lösung
{: #os-resolution}

Sie werden dazu aufgefordert, einen anderen Plan auszuwählen, um diesen Fehler zu vermeiden.


### Fehler beim Abrufen des Codes während der Projekterstellung
{: #code}

Es wird eventuell der folgende Fehler angezeigt, wenn Sie das {{site.data.keyword.dev_cli_short}} zum Erstellen eines Projekts verwenden:
	
```
FAILED
Project created, but could not get code
https://console.ng.bluemix.net/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}
	

#### Ursache
{: #code-cause}

Dieser Fehler tritt aufgrund einer internen Zeitlimitüberschreitung auf.
	

#### Lösung
{: #code-resolution}

Sie können den Code auf eine der folgenden Arten abrufen:

* Führen Sie den folgenden Befehl in der Befehlszeilenschnittstelle aus:

   ```
   bx dev code <your-project-name>
   ```
   {: codeblock}

   Ersetzen Sie `<your-project-name>` durch den Projektnamen, den Sie während der Projekterstellung angegeben haben.

* Verwenden Sie die {{site.data.keyword.dev_console}}.

	1. Verwenden Sie Ihr [Projekt ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](https://console.{DomainName}/developer/projects "Symbol für externen Link") in der {{site.data.keyword.dev_console}} und klicken Sie auf **Code abrufen**.

	2. Klicken Sie auf **Code generieren**.

	3. Klicken Sie nach der Generierung des Codes auf **Code herunterladen**.


### Fehler beim Ausführen von `bx dev run` für Node.js-Projekte
{: #node}

Es wird eventuell der folgende Fehler angezeigt, wenn Sie `bx dev run` mit dem {{site.data.keyword.dev_cli_short}} für Node.js-Web- oder BFF-Projekte ausführen:

```
module.js:597
  return process.dlopen(module, path._makeLong(filename));
                 ^

Error: /app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/appmetrics.node: invalid ELF header
    at Error (native)
    at Object.Module._extensions..node (module.js:597:18)
    at Module.load (module.js:487:32)
    at tryModuleLoad (module.js:446:12)

    at Function.Module._load (module.js:438:3)
    at Module.require (module.js:497:17)
    at require (internal/module.js:20:19)
    at Object.<anonymous> (/app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/index.js:25:13)
    at Module._compile (module.js:570:32)
    at Object.Module._extensions..js (module.js:579:10)
```
{: codeblock}


#### Ursache
{: #node-cause}
   
Dieser Fehler tritt auf, wenn das Modul `appmetrics` in einer anderen Architektur installiert wird. Native NPM-Module, die in einer Architektur installiert sind, funktionieren nicht in einer anderen. Die im Lieferumfang enthaltenen Docker-Images basieren auf einem Linux-Kernel.


#### Lösung
{: #node-resolution}

Löschen Sie den Ordner `node_modules` und führen Sie den Befehl `bx dev run` erneut aus.


<!--
## Troubleshooting techniques
{: #tstechniques}
-->

<!-- Add a heading and content for how to get help and support. Use this template for beta and GA services:  -->


## Hilfe und Unterstützung anfordern
{: #gettinghelp}

Falls Sie Probleme oder Fragen zur {{site.data.keyword.Bluemix_notm}} {{site.data.keyword.dev_console}} oder zum {{site.data.keyword.dev_cli_notm}} haben, können Sie Hilfe anfordern, indem Sie in einem Forum nach Informationen suchen oder Fragen stellen. Sie können auch ein Support-Ticket öffnen.

Wenn Sie Beiträge in den Foren posten, können Sie Ihre Fragen so markieren, dass die {{site.data.keyword.Bluemix_notm}}-Entwicklungsteams benachrichtigt werden. 

<!--Insert the appropriate Stack Overflow tag for your service for <service_keyword> in URL and text below:  -->

Wenn Sie technische Fragen zum Entwickeln oder Bereitstellen einer App mit der {{site.data.keyword.dev_console}} oder dem {{site.data.keyword.dev_cli_notm}} haben:

* Senden Sie Ihre Frage an [Stacküberlauf ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](http://stackoverflow.com/search?q=bluemix-dev-services+ibm-bluemix "Symbol für externen Link") und markieren Sie Ihre Frage mit `bluemix-dev-services` und `ibm-bluemix`.
* Senden Sie Ihre Frage an [Slack ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](http://ibm-cloud-tech.slack.com/ "Symbol für externen Link") im `bluemix-dev-services`-Kanal. [Melden Sie sich heute an ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](http://ibm.biz/IBMCloudNativeSlack "Symbol für externen Link") an.


<!--Insert the appropriate dW Answers tag for your service for <service_keyword> in URL below:  -->
<!--
* For questions about the service and getting started instructions, use the [IBM developerWorks dW Answers ![External link icon](../icons/launch-glyph.svg "External link icon")](https://developer.ibm.com/answers/topics/bluemix-dev-services/?smartspace=bluemix) forum. Include the  "bluemix-dev-services" and "bluemix" tags.
* -->

Weitere Information zur Nutzung der Foren finden Sie unter [Hilfe aufrufen ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](/docs/support/index.html#getting-help "Symbol für externen Link").

Informationen zum Öffnen eines {{site.data.keyword.IBM}} Support-Tickets oder zu den Support-Leveln und der Dringlichkeit von Tickets finden Sie unter [Unterstützung anfordern ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](/docs/support/index.html#contacting-support "Symbol für externen Link").

<!--Add a heading and content for how to get help. (Support not available for experimental.) Use this template for experimental services:  -->

