---
title: Bereitstellen von Skype Connectivity in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Zusammenfassung: Erfahren Sie, wie Sie Skype for Business Server mit Skype Consumer verbinden. Wird auch als Skype-Konnektivität bezeichnet.'
ms.openlocfilehash: 9c5f7f5c275b60c5b59dc43fe0a9b4a5c9b1514b
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574064"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Bereitstellen von Skype Connectivity in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie Skype for Business Server mit Skype Consumer verbinden. Wird auch als Skype-Konnektivität bezeichnet.
  
In diesem Artikel wird die Bereitstellung für Skype Connectivity erläutert.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Übersicht über Skype-Konnektivität für IT-Experten

Skype Connectivity bietet Skype for Business-Benutzern die Möglichkeit, nach Skype-Benutzern zu suchen und diese hinzuzufügen. Skype Connectivity ist ein Feature von Skype for Business, mit dem Sie die Verbund- und Verzeichnissuche mit Skype-Benutzern aktivieren können. Nachdem Sie Skype Connectivity aktiviert haben, können Ihre Skype for Business-Benutzer nach Skype-Benutzern suchen und diese hinzufügen.
  
## <a name="skype-directory-search"></a>Skype-Verzeichnissuche

Die Skype -Verzeichnissuche bietet Skype for Business-Benutzern die Möglichkeit, nach Skype-Kontakten zu suchen. Mit der Suchfunktion können Benutzer mithilfe der folgenden Optionen suchen:
  
- **Suchen nach Anzeigename, Beispiel "John Doe"** – Dies kann viele Ergebnisse zurückgeben, sodass Sie möglicherweise nicht finden, was Sie suchen.
    
- **Suchen nach Anzeigename und Standort, Beispiel "John Doe in Barcelona"** – Dadurch werden die Ergebnisse der Suche erheblich reduziert.
    
- **Suchen per E-Mail, Beispiel "johndoe@outlook.com"** – Dies sollte in den meisten Fällen ein Ergebnis zurückgeben. die, die der angegebenen E-Mail genau entspricht. Wenn jedoch dieselbe E-Mail mehreren Konten zugeordnet ist, können mehrere Ergebnisse zurückgegeben werden.
    
- **Suchen nach Telefonnummer, Beispiel "123-123-1234"** – Dies sollte in den meisten Fällen ein Ergebnis zurückgeben. das Telefon, das dem angegebenen Telefon genau entspricht. Die Telefonnummer muss die Ländercode enthalten (d. h. 1-xxx-yyy-zzzz). Wenn dieselbe Telefonnummer mehreren Konten zugeordnet ist, können mehrere Ergebnisse zurückgegeben werden.
    
- **Suche nach Skype-Name, Beispiel "JohnDoe1456"** – Wenn genaue Übereinstimmung gefunden wird, wird sie als erstes Ergebnis zurückgegeben. Andere mögliche Übereinstimmungen mit "Name" können zurückgegeben werden.
    
    > [!NOTE]
    > Die Skype-Verzeichnissuche muss mit den folgenden IP-Adressen an Port 443 kommunizieren können: 104.40.75.246, 23.101.135.34 und 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Unterstützte Bereitstellungsmatrix für die Skype Directory-Suche

In der folgenden Tabelle ist die Unterstützung für die Skype-Verzeichnissuche aufgeführt.
  

||**Skype for Business Server Front End**|**Lync Server 2013 (oder älter) Front-End**|**Comments**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server Edge  <br/> |Unterstützt  <br/> |Nicht unterstützt  <br/> |Skype for Business Server und Edge sind Voraussetzungen für die Skype-Verzeichnissuche  <br/> |
|Skype for Business Server Edge + Lync Server 2013 Edge nebeneinander bereitgestellt  <br/> |Unterstützt  <br/> |Nicht unterstützt  <br/> |Skype Directory Search-Datenverkehr fließt über Skype for Business Server-Edgeserver. Der Verbunddatenverkehr durchgeht den vom Administrator konfigurierten Edge. Beispielsweise könnte der Administrator weiterhin Verbunddatenverkehr über Lync Server 2013-Edgeserver senden, die die Skype -Verzeichnissuche nicht unterstützen würden.  <br/> |
|Lync Server 2013 (oder älter) Edge  <br/> |Nicht unterstützt  <br/> |Nicht unterstützt  <br/> ||
   
> [!NOTE]
> Der auf Skype for Business Server-Front-End ausgeführte Adressbuchdienst findet den Edge durch das Vorhandensein des Skype-Suchports 4443 auf dem Edgeserver. 
  
> [!NOTE]
> Falls ein Kunde mehrere Standorte in seiner lokalen Bereitstellung hat und nur einen Skype for Business Server-Edgeserver/-Pool bereitgestellt hat, wird der Suchdatenverkehr von allen Standorten über den einzelnen verfügbaren Edgeserver ausgeführt. Der Administrator muss sicherstellen, dass die Pools von allen Websites auf den bereitgestellten Skype for Business Server-Edgeserver/-pool zugreifen können. 
  
> [!NOTE]
> Der Skype-Graph-Dienst drosselt Suchanfragen von lokalen oder Microsoft 365- oder Office 365-Kunden, wenn die Anforderungsrate 15 Anforderungen/Sekunde überschreitet. 
  
> [!NOTE]
> Für lokale Großunternehmen müssen die Domänen einer Allowlist mit dem Skype-Suchdienst hinzugefügt werden, um höhere Anforderungsraten zu ermöglichen.
  
> [!NOTE]
> Skype for Business Server drosselt eingehende Anforderungen, wenn zu viele ausstehende Anforderungen in der Warteschlange vorhanden sind. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>Bereitstellen von Skype Connectivity for Skype for Business Online

Skype Connectivity ist auch ein Feature von Skype for Business Online, das Teil von Microsoft 365 und Office 365 ist. Sie können das Skype Connectivity-Feature über das Skype for Business Administration Center im Microsoft 365 Admin Center aktivieren.
  
Für Microsoft 365 Midsize Business, Office 365 Enterprise, Microsoft 365 Education und Office 365 for Government: Melden Sie sich beim Microsoft 365 Admin Center an, und navigieren Sie zum Skype for Business Administration Center. Wechseln Sie zu Externe Kommunikation. Klicken Sie unter Anbieter für öffentliche Im-Im-Dienste auf Aktivieren. Wenn Sie den Zugriff einzelner Benutzer auf Skype Connectivity steuern möchten, können Sie dazu die Einstellungen für die externe Kommunikation einzelner Benutzer bearbeiten.
  
For Office 365 Small Business Premium: Sign in to Office 365, and go to Admin \> Service Settings \> Instant messaging, meetings and conferencing. Aktivieren Sie externe Kommunikation. Der Switch Externe Kommunikation aktiviert sowohl Die Skype-Konnektivität als auch die Kommunikation mit anderen Organisationen, die Skype for Business verwenden.
  
Weitere Informationen zur Skype for Business Online-Verwaltung finden Sie unter:
  
- [Zulassen, dass Benutzer externe Skype for Business-Benutzer kontaktieren](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Probieren Sie aus, wenn Externe Skype for Business- oder Skype-Kontakte nicht im Chat angezeigt werden können](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Hinzufügen eines Kontakts in Skype for Business](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administratoren: Konfigurieren von Skype for Business-Einstellungen für einzelne Benutzer](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Bereitstellen von Skype Connectivity for Skype for Business Server

Skype for Business Server verwendet die Verbundzugriffsarchitektur, um die Konnektivität mit Skype zu unterstützen. Diese Konnektivität ermöglicht Es Ihren Skype for Business Server-Benutzern, Skype hinzuzufügen. Skype-Clients können auch Skype for Business-Benutzer zu ihrer Kontaktliste hinzufügen. Basierend auf in Skype for Business Server festgelegten Richtlinien können Benutzer über Chat kommunizieren, sich gegenseitig ihre Anwesenheit ansehen und Audio- und Videoanrufe initiieren. Die Skype-Konnektivität ist auch ein Feature von Skype for Business Online und kann für Skype for Business Online-Kunden über das Skype for Business Administration Center im Microsoft 365 Admin Center aktiviert werden.
  
> [!NOTE]
> Wenn Skype for Business Server bereits für die Verbindung mit Windows Messenger mithilfe von Public Instant Messaging Connectivity (PIC) konfiguriert ist, ist Ihre Bereitstellung bereits für die Skype-Konnektivität konfiguriert. Die einzige Änderung, die Sie in Betracht ziehen möchten, ist, Ihren vorhandenen Messenger -PIC-Eintrag in Skype umzubenennen. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Die Bereitstellungswebsite für öffentliche Chatverbindungen in Skype for Business Server ist nicht mehr verfügbar.

Die Website, die früher zum manuellen Bereitstellen des Verbunds zwischen lokalen Skype for Business-Bereitstellungen und Skype verwendet wurde, ist nicht mehr erforderlich und wird am 15.08.2019 beendet. Der Partnerverbund mit Skype nutzt jetzt die Partnersuche, die denselben Mechanismus für den Partnerverbund mit Skype for Business Online benötigt.

Für die Kommunikation zwischen allen lokalen Skype for Business-Bereitstellungen und Skype-Benutzern über die vorhandene Public Chat-Infrastruktur muss die lokale Edgeserverkonfiguration nun mit Skype for Business Online kompatibel sein.

> [!NOTE]
> Die meisten Kunden benötigen keine Aktion, einschließlich aller Bereitstellungen, die mit Skype for Business Online zusammenarbeiten.
  
Lokale Bereitstellungen sind erforderlich, um einen DNS-SRV-Verbunddatensatz für jede Domäne zu veröffentlichen, die sie hosten. Anleitungen sind in der [DNS-Planung verfügbar.](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning) Jede Domäne muss durch DNS-SRV-Abfrage in einen Edgeserver-FQDN aufgelöst werden, der eine Suffix-Übereinstimmung auf oberster Ebene der Domäne erfüllt. Betrachten Sie beispielsweise die Domäne "contoso.com":

|**Gültige FQDNs**|**Kommentar**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |In jedem Fall muss der genaue FQDN entweder im SN oder im SAN des auf dem Edgeserver installierten externen Zertifikats vorhanden sein.   |
|access.contoso.com   ||
|**Ungültige FQDNs**|**Grund**|
|sip.contoso-edge.com   |Keine Suffix-Übereinstimmung.  |
|sip.it.contoso.com   |Keine Suffix-Übereinstimmung auf oberster Ebene.   |

Weitere Anleitungen zu externen Zertifikaten finden Sie unter [Certificate planning](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning).

#### <a name="faqs"></a>Häufig gestellte Fragen

**Warum wird die Bereitstellungswebsite heruntergefahren?**
Der im Jahr 2006 bereitgestellte bereitstellungsmechanismus (public IM, PIC) (pic.lync.com) ist nicht mehr einsatzfähig und wird am 15.08.2019 beendet. Stattdessen wird vom öffentlichen Chatverbund das gleiche Verbundmodell angenommen, das von Skype for Business Online verwendet wird, das auch als "Partnerermittlung" bezeichnet wird, wobei eine lokale Bereitstellung von den DNS-SRV-Einträgen des Verbunds öffentlich ermittelt werden kann.

**Bedeutet diese Änderung, dass der Verbund für öffentliche Öffentlichen Dienst veraltet ist?**
Nein. Der öffentliche Chatverbund wird weiterhin für viele Jahre unterstützt, wahrscheinlich bis das lokale Produkt von Skype for Business das Ende des Lebenszyklus erreicht hat.

**Unser Unternehmen hat eine Hybridbeziehung (freigegebener Adressraum) mit Skype for Business Online, sind wir betroffen?**
Nein, da Sie bereits einen Verbund mit Skype for Business Online führen, hat diese Änderung keine Auswirkungen auf Sie.
 
**Bedeutet diese Änderung, dass unser Unternehmen den Partnerverbund mit Skype for Business Online aktivieren muss?**
Nein. Wenn Ihre Edgeserverproxyeinstellungen den Verbund mit dem Skype for Business Online-Hostinganbieter (sipfed.online.lync.com) nicht aktivieren, hat diese Änderung keine Auswirkungen darauf. Die gleichen DNS- und Zertifikatanforderungen, die für das Partnering mit Skype for Business Online gelten, gelten jetzt jedoch auch für das Partnering mit Skype-Benutzern.
 
**Unser Unternehmen ist groß und kann seine Edgekonfiguration aus Gesetzlichen/Compliance-/etc-Gründen nicht ändern ... Was können wir tun?**
Jede lokale Organisation, die ihre Edgeserverkonfiguration nicht wie angegeben ändern kann, sollte sich so schnell wie möglich an den Produktsupport senden.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Aktivieren der Verbund- und Öffentlichen Im-Im-In-Verbindung (PIC)

Konzentrieren Sie sich nun auf die Skype for Business Server-Umgebung und administrative Aufgaben, die zum Konfigurieren von Skype Connectivity erforderlich sind. In diesem Abschnitt wird davon ausgegangen, dass der Administrator Skype for Business Server bereitgestellt und den externen Zugriff konfiguriert hat, auch als Edgeserver bezeichnet. 
  
Es sind drei primäre Schritte erforderlich, um den Verbund und PIC zu aktivieren. Diese sind:
  
1. Konfigurieren von Verbund und PIC
    
2. Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Verbundbenutzerzugriffs
    
3. Konfigurieren der Skype PIC-Anbietereinstellung
    
#### <a name="1-configure-federation-and-pic"></a>1. Konfigurieren von Verbund und PIC

Der Verbund ist erforderlich, damit Skype-Benutzer mit Skype for Business-Benutzern in Ihrer Organisation kommunizieren können. Public Instant Messaging Connectivity (PIC) ist eine Verbundklasse und muss so konfiguriert werden, dass Ihre Skype for Business-Benutzer mit Skype-Benutzern kommunizieren können. Verbund und PIC werden mithilfe der Skype for Business Server-Systemsteuerung konfiguriert.
  
> [!NOTE]
> Der PIC-Verbund wird von Produktversionen vor Lync Server 2010 (Live Communication Server, Office Communications Server) nicht mehr unterstützt. Zu den unterstützten Plattformen für den PIC-Verbund gehören Skype for Business Server, Lync Server 2013 und Lync Server 2010. 
  
Der Verbund ist erforderlich, damit Skype-Benutzer mit Skype for Business-Benutzern in Ihrer Organisation kommunizieren können. Public Instant Messaging Connectivity (PIC) ist eine Verbundklasse und muss so konfiguriert werden, dass Ihre Skype for Business Server-Benutzer mit Skype-Benutzern kommunizieren können. Verbund und PIC werden mithilfe des Edgekonfigurationsdialogfelds der Skype for Business Server-Systemsteuerung konfiguriert, wie in der Abbildung dargestellt.
  
![Definieren eines neuen Edgepools](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Die Attribute EnableSkypeIdRouting und EnableSkypeDirectorySearch müssen in den Einstellungen des öffentlichen Anbieters (siehe spätere Anweisungen) auf true festgelegt werden, damit die Suche funktioniert. 
  
Dadurch werden die verwaltungstechnischen Aufgaben abgeschlossen, die auf dem Server ausgeführt werden müssen. Sie sind jetzt für Skype Connectivity eingerichtet.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Verbundbenutzerzugriffs

Mithilfe der Skype for Business Server-Systemsteuerung muss ein Administrator eine oder mehrere Richtlinien für den externen Benutzerzugriff konfigurieren, um zu steuern, ob Skype-Benutzer mit internen Skype for Business Server-Benutzern zusammenarbeiten können.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Konfigurieren der Skype PIC-Anbietereinstellung

Mithilfe der Skype for Business Server-Verwaltungsshell muss ein Administrator die Skype for Business-Clientrichtlinie so konfigurieren, dass Skype als zusätzlicher PIC-Anbieter angezeigt wird. 
  
> [!NOTE]
> Benutzer der Public Instant Messaging Connectivity (PIC)-Dienstanbieter können erst an Chatnachrichten oder Konferenzen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine Richtlinie (Schritt 2, weiter oben in diesem Verfahren) zur Unterstützung der Konnektivität mit öffentlichen Chatnachrichten konfigurieren. 
  
Für neue Installationen können Sie Skype Connectivity konfigurieren, indem Sie einen öffentlichen Skype-Anbieter mithilfe der Skype for Business Server-Systemsteuerung aktivieren, wie in der Abbildung dargestellt.
  
![SIP-Partnerverbundanbieter](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Um Skype Connectivity beim Upgrade auf Skype for Business Server zu konfigurieren, müssen Sie den vorhandenen öffentlichen Skype-Anbieter entfernen und erneut hinzufügen. 
  
Das Konfigurieren von Skype Connectivity kann auch nur mit PowerShell durchgeführt werden. So konfigurieren Sie Skype Connectivity mithilfe von PowerShell:
  
1. Öffnen Sie auf einem Skype for Business Server-Front-End-Server die Skype for Business Server-Verwaltungsshell.
    
2. Führen Sie die folgenden beiden Befehle aus:
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Wenn Sie noch keinen PIC-Anbieter in Ihrer Umgebung haben und einen neuen PIC-Anbieter erstellen, müssen Sie das cmdlet Remove-CsPublicProvider ausführen. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    Was tun die weniger offensichtlichen Parameter?
    
   - ProxyFqdn: Speicherort des Skype-Verbundrands (im Besitz von Microsoft/verwaltet)
    
   - IconURL: Symbol, das vom Lync &amp; Skype for Business-Client verwendet wird, um Skype-Kontakte visuell zu identifizieren
    
   - NameDecorationRoutingDomain und NameDecorationExcludedDomainList: Wenn Sie diese Festlegen festlegen, können Benutzer die MSAs von Skype-Benutzern eingeben, ohne wissen zu müssen, wie Nicht-Microsoft-Domänen mit "msn.com" eingerichtet werden müssen. Dadurch ist es nicht mehr nötig, "user(contoso.com)@msn.com" für alle Domänen ein, die SICH NICHT in der ExcludedDomainList befinden. Der SfB-Client formatiert die MSA automatisch, wenn sich die Domäne NICHT in der Liste Ausgeschlossen befindet. Wir haben die gängigsten Microsoft Account-Domänen zur ausgeschlossenen Liste hinzugefügt.
    
     > [!NOTE]
     > Der öffentliche Anbieter muss entfernt und neu hinzugefügt werden, wenn Änderungen vorgenommen werden. Änderungen sind nicht zulässig. 
  
     > [!NOTE]
     > In Lync Server 2013 CU5 &amp; Lync-Desktopclient in Office 2013 SP1 hinzugefügt, verbessern nameDecorationRoutingDomain und NameDecorationExcludedDomainList die Situation, dass Lync-Benutzer, die Skype-Kontakte hinzufügen, zum "Schmücken" von Nicht-Microsoft-Domänen zum Identifizieren und Routen an Skype erforderlich sind (format: user(contoso.com)@msn.com). Diese neuen Einstellungen ermöglichen die automatische Formatierung der Eingabe des Adressbenutzers im Dialogfeld "Skype-Kontakt hinzufügen" mit der NameDecorationRoutingDomain (die auf msn.com festgelegt werden sollte), wenn sie nicht die Domänen im NameDecorationExcludedDomainList enthält (wir können derzeit msn.com, live.com, Hotmail.com, outlook.com unterstützen). 
  
3. Über einen Skype for Business-Client können Benutzer nun nach einem Skype-Benutzer suchen und diesen hinzufügen.
    
## <a name="clients-and-interoperability-matrix"></a>Clients und Interoperabilitätsmatrix

In der folgenden Tabelle wird der Status der Interop zwischen der neuesten Version von Skype Consumer und der neuesten Version von Skype for Business aufgeführt.
  

|**Skype-Clients**|**Hinzufügen von Kontakten, Telefonanrufen, Anwesenheits-, Audio- und Videoanrufen**|**Kommentar**|
|:-----|:-----|:-----|
|Skype Windows Desktop  <br/> |7.6 oder höher, Windows XP und höher  <br/> |**NEU**: Unterstützung für Windows Skype-Client, der unter Windows XP ausgeführt wird, und Windows Vista (erfordert die neueste **Clientversion 7.26 oder höher)** <br/> |
|Skype Mobile – Android Phone und Tablet  <br/> |6.19 oder höher mit Android OS, Version 4.0.3 oder höher  <br/> |Geräte mit niedriger Spezifikation unterstützen möglicherweise keine Videoanrufe  <br/> |
|Skype Mobile – iOS  <br/> |6.11 oder höher, auf IOS 7 oder höher  <br/> |Nicht unterstützt werden iPhone 4 und früher, iPod 4. Generation und frühere iPad 1. Generation  <br/> |
|Skype Mac  <br/> |7.19 oder höher unter Mac OS X 10.9 (Mavericks) oder höher  <br/> |Erfordert Mac OSX 10.9 oder höher  <br/> |
|Skype Universal Windows App (Windows 10) Desktop und Mobile  <br/> |Windows 10 (Redstone 1 Update oder höher)  <br/> |Windows Universal App erhält update im Herbst 2016 und fügt Die Interopunterstützung hinzu  <br/> |
   
In der folgenden Tabelle wird der Status der Interop zwischen der neuesten Version von Skype for Business und der neuesten Version von Skype Consumer erläutert. 
  
|**Client**|**Skype-Verzeichnissuche und Hinzufügen von Kontakten**|**Skype A/V, Chat-Inop**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |Ja  <br/> |Ja  <br/> |
|Skype for Business auf dem Mac  <br/> |Kann hinzugefügt werden (keine Suche)  <br/> |Ja  <br/> |
|Lync Desktop 2013  <br/> |Kann hinzugefügt werden (keine Suche)  <br/> |Ja  <br/> |
|Lync Web App – online und lokal  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |
|Lync Mobile – Windows Phone  <br/> |In Kürze verfügbar  <br/> |Ja  <br/> |
|Lync Mobile – Android  <br/> |In Kürze verfügbar  <br/> |Ja  <br/> |
|Lync Mobile – iOS  <br/> |In Kürze verfügbar  <br/> |Ja  <br/> |
|Lync-Raumsystem  <br/> |In Kürze verfügbar  <br/> |Ja  <br/> |
|Lync Modern App (Win 8.1)  <br/> |Ja  <br/> |Ja  <br/> |
|Lync Mac 2011  <br/> |Kann hinzugefügt werden (keine Suche)  <br/> |Ja  <br/> |
|Lync Desktop 2010  <br/> |Kann hinzugefügt werden (keine Suche)  <br/> |Ja  <br/> |
|Lync Phone Edition  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |
|Lync Attendant  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |
   
