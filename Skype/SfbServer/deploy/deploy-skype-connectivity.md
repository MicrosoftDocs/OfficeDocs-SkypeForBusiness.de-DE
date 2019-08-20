---
title: Bereitstellen von Skype-Konnektivität in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Skype for Business Server mit Skype Consumer verbinden. Wird auch als Skype-Konnektivität bezeichnet.'
ms.openlocfilehash: 4a335d2ec8e20310a34ce1bdfc8f39fe9b1117ee
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464600"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Bereitstellen von Skype-Konnektivität in Skype for Business Server

**Zusammenfassung:** Hier erfahren Sie, wie Sie Skype for Business Server mit Skype Consumer verbinden. Wird auch als Skype-Konnektivität bezeichnet.
  
Dieser Artikel führt Sie durch die Bereitstellung für Skype-Konnektivität.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Übersicht über Skype-Konnektivität für IT-Experten

Skype-Konnektivität bietet Skype for Business-Benutzern die Möglichkeit, Skype-Nutzer zu suchen und hinzuzufügen. Skype Connectivity ist eine Funktion von Skype for Business, mit der Sie die Föderations-und Verzeichnissuche mit Skype-Nutzern aktivieren können. Nachdem Sie die Skype-Konnektivität aktiviert haben, können Ihre Skype for Business-Benutzer Skype-Nutzer suchen und hinzufügen.
  
## <a name="skype-directory-search"></a>Skype-Verzeichnissuche

Die Funktion für die Skype-Verzeichnissuche ermöglicht Skype for Business-Benutzern, nach Skype-Kontakten zu suchen. Mit der Suchfunktion können Benutzer folgende Suchvorgänge ausführen:
  
- **Suche nach Anzeigename, Beispiel "John Doe"** – Dies kann viele Ergebnisse zurückgeben, sodass Sie möglicherweise nicht finden, wonach Sie suchen.
    
- **Suchen nach Anzeigename und Standort, Beispiel "Johannes Doe in Barcelona"** – dadurch werden die Suchergebnisse erheblich verringert.
    
- **Suchen Sie per e-Mail, beispielsweise "JohnDoe@Outlook.com"** – dies sollte in den meisten Fällen ein Ergebnis zurückgeben; diejenige, die genau der angegebenen e-Mail entspricht. Wenn dieselbe e-Mail-Adresse aber mehr als einem Konto zugeordnet ist, werden möglicherweise mehrere Ergebnisse zurückgegeben.
    
- **Suche nach Telefonnummer, Beispiel "123-123-1234"** – in den meisten Fällen sollte dies ein Ergebnis zurückgeben; diejenige, die genau dem angegebenen Telefon entspricht. Die Telefonnummer muss die Landesvorwahl (dh 1-xxx-yyy-zzzz) umfassen. Wenn dieselbe Telefonnummer mehr als einem Konto zugeordnet ist, werden möglicherweise mehrere Ergebnisse zurückgegeben.
    
- **Suche nach Skype-Namen, Beispiel "JohnDoe1456"** – wenn genau Übereinstimmung gefunden wird, wird es als erstes Ergebnis zurückgegeben. Andere mögliche "Name"-Übereinstimmungen können zurückgegeben werden.
    
    > [!NOTE]
    > Die Suche im Skype-Verzeichnis muss in der Lage sein, mit den folgenden IP-Adressen an Port 443 zu kommunizieren: 104.40.75.246, 23.101.135.34 und 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Unterstützte Bereitstellungsmatrix für die Skype-Verzeichnissuche

In der folgenden Tabelle ist angegeben, ob die Skype-Verzeichnissuche unterstützt wird.
  

||**Skype for Business Server-Front-End**|**Lync Server 2013-Front-End-Server (oder älter)**|**Anmerkungen**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server-Edge  <br/> |Unterstützt  <br/> |Nicht unterstützt  <br/> |Skype for Business Server und Edge sind Voraussetzungen für die Skype-Verzeichnissuche  <br/> |
|Side-by-Side-Bereitstellung von Skype for Business Server Edge + lync Server 2013 Edge  <br/> |Unterstützt  <br/> |Nicht unterstützt  <br/> |Der Datenverkehr der Skype-Verzeichnissuche wird über Skype for Business Server-Edgeserver verarbeitet. Der Partnerverbunddatenverkehr wird über Edgeserver verarbeitet, die vom Administrator konfiguriert wurden. Beispielsweise kann der Administrator festlegen, dass der Partnerverbunddatenverkehr weiterhin über Lync Server 2013-Edgeserver gesendet wird, die die Skype-Verzeichnissuche nicht unterstützen.  <br/> |
|Lync Server 2013-Edgeserver (oder älter)  <br/> |Nicht unterstützt  <br/> |Nicht unterstützt  <br/> ||
   
> [!NOTE]
> Der Adressbuchdienst, der auf dem Skype for Business Server-Front-End ausgeführt wird, findet den Vorteil durch das vorhanden sein des Skype Search Port 4443 auf dem Edgeserver. 
  
> [!NOTE]
> Wenn ein Kunde über mehrere Websites in der lokalen Bereitstellung verfügt und nur einen Skype for Business Server-Edgeserver/-Pool bereitgestellt hat, wird der Such Datenverkehr von allen Websites über den einzelnen verfügbaren Edgeserver durchlaufen. Der Administrator muss sicherstellen, dass die Pools aller Websites auf den bereitgestellten Skype for Business Server-Edgeserver/-Pool zugreifen können. 
  
> [!NOTE]
> Der Skype-Diagrammdienst schränkt die Suchanforderungen von lokalen Kunden bzw. Office 365-Kunden ein, wenn die Anforderungsrate 15 Anforderungen pro Sekunde überschreitet. 
  
> [!NOTE]
> Für lokale Kunden in großen Unternehmen müssen die Domänen mit dem Skype-Suchdienst in die Genehmigungsliste aufgenommen werden, um höhere Anforderungsraten zuzulassen. 
  
> [!NOTE]
> Skype for Business Server wird eingehende Anforderungen Drosseln, wenn in der Warteschlange zu viele ausstehende Anforderungen vorhanden sind. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a>Bereitstellen der Skype-Konnektivität für Skype for Business Online in Office 365

Die Skype-Konnektivität ist auch eine Funktion in Skype for Business Online, das in Office 365 enthalten ist. Sie können die Skype-Konnektivität im Skype for Business Admin Center im Office 365-Portal aktivieren.
  
Für Office 365 Midsize Business, Office 365 Enterprise, Office 365 Education und Office 365 für Behörden: Melden Sie sich beim Office 365-Portal an und öffnen Sie das Skype for Business Admin Center. Wechseln Sie zu „Externe Kommunikation“. Klicken Sie unter „Öffentliche Anbieter von Chatdiensten“ auf „Aktivieren“. Wenn Sie den Zugriff einzelner Benutzer auf die Skype-Konnektivität steuern möchten, können Sie die Einstellungen für die externe Kommunikation einzelner Benutzer bearbeiten.
  
Für Office 365 Small Business Premium: Anmelden bei Office 365 und wechseln zu den Administrator \> Diensteinstellungen \> Instant Messaging, Besprechungen und Konferenzen. Aktivieren Sie „Externe Kommunikation“. Der Schalter „Externe Kommunikation“ dient zum Aktivieren der Skype-Konnektivität und der Kommunikation mit anderen Unternehmen, die Skype for Business nutzen.
  
Weitere Informationen zur Skype for Business Online-Verwaltung finden Sie unter:
  
- [Zulassen, dass Benutzer externe Skype for Business-Benutzer kontaktieren](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Was Sie versuchen können, wenn Sie keine Skype for Business-oder Skype-externen Kontakte haben](https://support.office.com/en-us/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Hinzufügen eines Kontakts in Skype for Business](https://support.office.com/en-US/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administratoren: Skype for Business-Einstellungen für einzelne Benutzer konfigurieren](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Bereitstellen von Skype-Konnektivität für Skype for Business Server

Skype for Business Server verwendet die Verbund Zugriffs Architektur, um die Konnektivität mit Skype zu unterstützen. Dank dieser Konnektivität können Skype for Business Server-Benutzer Skype hinzufügen. Skype-Clients können ihren Kontaktlisten auch Skype for Business-Benutzer hinzufügen. Basierend auf den in Skype for Business Server festgelegten Richtlinien können Benutzer über Chats kommunizieren, sich gegenseitig unterhalten und Audio-und Videoanrufe initiieren. Die Skype-Konnektivität ist auch eine Funktion in Skype for Business Online und kann für Skype for Business Online-Kunden im Skype for Business Admin Center im Office 365-Portal aktiviert werden.
  
> [!NOTE]
> Wenn Skype for Business Server bereits für die Herstellung der Verbindung mit Windows Messenger über PIC (Public Instant Messaging Connectivity, Verbindung mit öffentlichen Chatdiensten) konfiguriert wurde, ist Ihre Bereitstellung schon für die Skype-Konnektivität konfiguriert. Als einzige Änderung sollten Sie ggf. den vorhandenen Messenger PIC-Eintrag in „Skype“ umbenennen.  
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Die Bereitstellungswebsite für den öffentlichen Chat in Skype for Business Server steht nicht mehr zur Verfügung.

Die Website, die früher für die manuelle Bereitstellung der Föderation zwischen Skype for Business-lokalen Bereitstellungen und Skype verwendet wurde, ist nicht mehr erforderlich und wird auf 8/15/2019 heruntergefahren. In der Föderation mit Skype wird nun die Verbundpartner-Discovery verwendet, die derselbe Mechanismus ist, der für die Föderation mit Skype for Business Online erforderlich ist.

Die Kommunikation zwischen einer lokalen Skype for Business-Bereitstellung und Skype-Benutzern über die vorhandene öffentliche Chat-Infrastruktur erfordert jetzt, dass die lokale Edge-Server-Konfiguration mit Skype for Business Online kompatibel ist.

> [!NOTE]
> Die meisten Kunden benötigen keine Aktion, einschließlich aller Bereitstellungen, die mit Skype for Business Online zusammenlaufen.
  
Lokale Bereitstellungen sind erforderlich, um einen Verbund-DNS-SRV-Eintrag für jede Domäne zu veröffentlichen, die er hostet. Anleitungen finden Sie in der [DNS-Planung](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning). Jede Domäne muss durch eine DNS-SRV-Abfrage zu einem Edgeserver-FQDN aufgelöst werden, der eine Übereinstimmung auf oberster Ebene der Domäne erfüllt. Nehmen Sie beispielsweise die Domäne "contoso.com" in Frage:

|**Gültige FQDNs**|**Kommentar**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |In jedem Fall muss der exakte FQDN entweder im SN-oder im San des externen Zertifikats vorhanden sein, das auf dem Edgeserver installiert ist.   |
|access.contoso.com   ||
|**Ungültige FQDNs**|**Grund**|
|sip.contoso-edge.com   |Keine Suffix-Übereinstimmung.  |
|sip.it.contoso.com   |Das Suffix der obersten Ebene ist nicht identisch.   |

Weitere Anleitungen zu externen Zertifikaten finden Sie unter [Zertifikats Planung](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning).

#### <a name="faqs"></a>FAQs

**Warum wird die Bereitstellungswebsite heruntergefahren?**
Der in 2006 bereitgestellte öffentliche im (PIC)-Bereitstellungsmechanismus (PIC.lync.com) ist nicht mehr wartungsbar und wird auf 8/15/2019 beendet. Stattdessen übernimmt der öffentliche im-Verbund das gleiche Verbundmodell, das von Skype for Business Online verwendet wird, das unter dem Namen "Partner Discovery" bekannt ist, wodurch eine lokale Bereitstellung durch die DNS-SRV-Einträge der Föderation öffentlich auffindbar ist.

**Bedeutet diese Änderung, dass der öffentliche im-Verbund veraltet ist?**
Nummer Der öffentliche Chat-Verbund wird weiterhin viele Jahre lang unterstützt, wahrscheinlich, bis das Skype for Business-Produkt am Ende des Lebenszyklus erreicht ist.

**Unser Unternehmen eine Hybrid Beziehung (freigegebener Adressraum) mit Skype for Business Online hat, sind wir davon betroffen?**
Nein, da Sie bereits eine Föderation mit Skype for Business Online haben, hat diese Änderung keinen Einfluss auf Sie.
 
**Bedeutet diese Änderung, dass unser Unternehmen Föderation mit Skype for Business Online aktivieren muss?**
Nummer Wenn Ihre Edge-Server-Proxyeinstellungen die Föderation nicht mit dem Skype for Business Online-Hostinganbieter (sipfed.online.lync.com) aktivieren, wirkt sich diese Änderung nicht auf diese aus. Die gleichen DNS-und Zertifikatanforderungen, die für die Föderation mit Skype for Business Online gelten, gelten nun auch für die Föderation mit Skype-Nutzern.
 
**Unser Unternehmen ist groß und kann seine Edge-Konfiguration aufgrund behördlicher/Compliance/etc-Gründe nicht ändern... Was können wir tun?**
Jede lokale Organisation, die ihre Edge-Server-Konfiguration nicht wie angegeben ändern kann, sollte den Produktsupport so früh wie möglich erreichen.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Aktivieren von Partnerverbünden und Verbindungen mit öffentlichen Chatdiensten (PIC)

Konzentrieren Sie sich jetzt auf die Skype for Business Server-Umgebung und administrative Aufgaben, die für die Konfiguration der Skype-Konnektivität erforderlich sind. In diesem Abschnitt wird davon ausgegangen, dass der Administrator Skype for Business Server bereitgestellt und den externen Zugriff konfiguriert hat (auch als Edgeserver bezeichnet). 
  
Es gibt drei primäre Schritte zur Aktivierung des Partnerverbunds und der PIC:
  
1. Konfigurieren des Partnerverbunds und der PIC
    
2. Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Benutzerzugriffs im Partnerverbund
    
3. Konfigurieren der Einstellung des Skype PIC-Anbieters
    
#### <a name="1-configure-federation-and-pic"></a>1. Konfigurieren des Partnerverbunds und der PIC

Der Partnerverbund ist erforderlich, damit Skype-Benutzer mit Skype for Business-Benutzern in Ihrer Organisation kommunizieren können. PIC (Public Instant Messaging Connectivity, Verbindung mit öffentlichen Chatdiensten) ist eine Partnerverbundklasse und muss konfiguriert werden, damit Skype for Business-Benutzer mit Skype-Benutzern kommunizieren können. Partnerverbund und PIC werden mit der Skype for Business Server-Systemsteuerung konfiguriert.
  
> [!NOTE]
> PIC Federation wird von Produktversionen vor lync Server 2010 (Live Communication Server, Office Communications Server) nicht mehr unterstützt. Zu den unterstützten Plattformen für PIC Federation Gehören Skype for Business Server, lync Server 2013 und lync Server 2010. 
  
Der Partnerverbund ist erforderlich, damit Skype-Benutzer mit Skype for Business-Benutzern in Ihrer Organisation kommunizieren können. PIC ist eine Partnerverbundklasse und muss konfiguriert werden, damit Skype for Business Server-Benutzer mit Skype-Benutzern kommunizieren können. Partnerverbund und PIC werden im Dialogfeld zur Edgeserverkonfiguration der Skype for Business Server-Systemsteuerung konfiguriert.
  
![Neuen Edgepool definieren](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Die Attribute „EnableSkypeIdRouting“ und „EnableSkypeDirectorySearch“ müssen in den Einstellungen für öffentliche Anbieter auf „True“ festgelegt werden (siehe Anweisungen weiter unten), um die Suche ausführen zu können. 
  
Damit sind die Verwaltungsaufgaben abgeschlossen, die auf dem Server durchgeführt werden müssen. Die Skype-Konnektivität ist nun eingerichtet.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. Konfigurieren Sie mindestens eine Richtlinie zur Unterstützung des Zugriffs von Verbundbenutzern.

Der Administrator muss in der Skype for Business Server-Systemsteuerung mindestens eine Richtlinie für den Zugriff externer Benutzer konfigurieren, um zu steuern, ob Skype-Benutzer mit internen Skype for Business Server-Benutzern zusammenarbeiten können.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Konfigurieren der Skype PIC-Anbieter Einstellung

Der Administrator muss in der Skype for Business Server-Verwaltungsshell die Skype for Business-Clientrichtlinie so konfigurieren, dass Skype als weiterer PIC-Anbieter angezeigt wird.  
  
> [!NOTE]
> Benutzer der Dienstanbieter für öffentliche Instant Messaging-Konnektivität (PIC) können nicht an Chats oder Konferenzen in Ihrer Organisation teilnehmen, bis Sie auch mindestens eine Richtlinie (Schritt 2, weiter oben in diesem Verfahren) konfiguriert haben, um die Konnektivität öffentlicher Chats zu unterstützen. 
  
Für neue Installationen können Sie die Skype-Konnektivität konfigurieren, indem Sie wie in der Abbildung dargestellt einen öffentlichen Skype-Anbieter mithilfe der Skype for Business Server-Systemsteuerung aktivieren.
  
![SIP-Partnerverbundanbieter](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Um die Skype-Konnektivität beim Upgrade auf Skype for Business Server zu konfigurieren, müssen Sie den vorhandenen öffentlichen Skype-Anbieter entfernen und erneut hinzufügen. 
  
Die Skype-Konnektivität kann auch nur mit PowerShell konfiguriert werden. So konfigurieren Sie die Skype-Konnektivität mit PowerShell:
  
1. Öffnen Sie die Skype for Business Server-Verwaltungsshell auf einem Skype for Business Server-Front-End-Server.
    
2. Führen Sie die folgenden beiden Befehle aus:
    
   ```
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Wenn kein PIC-Anbieter in Ihrer Umgebung vorhanden ist und Sie einen neuen PIC-Anbieter erstellen, muss das Cmdlet „Remove-CsPublicProvider“ nicht ausgeführt werden.  
  
   ```
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    Welche Funktionen erfüllen die weniger offensichtlichen Parameter?
    
   - ProxyFqdn: Standort des Edgeservers im Skype-Partnerverbund (Eigentum/verwaltet von Microsoft)
    
   - IconURL: Symbol, das von &amp; lync Skype for Business-Client verwendet wird, um Skype-Kontakte visuell zu identifizieren
    
   - NameDecorationRoutingDomain und NameDecorationExcludedDomainList: Diese Einstellung ermöglicht es Benutzern, die MSAS von Skype-Benutzern einzugeben, ohne dass Sie über die "Verzierung" nicht-Microsoft-Domänen mit "MSN.com" Bescheid wissen müssen. Dadurch ist es nicht mehr erforderlich, "User (contoso. com) @MSN. com" für alle Domänen einzugeben, die nicht im ExcludedDomainList enthalten sind. Der SfB-Client formatiert automatisch das MSA, wenn die Domäne NICHT in der Excluded-Liste enthalten ist. Wir haben die am häufigsten verwendeten Microsoft-Kontodomänen der ausgeschlossenen Liste hinzugefügt.
    
     > [!NOTE]
     > Wenn Änderungen vorgenommen werden, müssen öffentliche Anbieter entweder und erneut hinzugefügt werden. Direkte Änderungen sind nicht zulässig. 
  
     > [!NOTE]
     > In lync Server 2013 CU5 &amp; lync-Desktop Client in Office 2013 SP1 wurden die NameDecorationRoutingDomain und NameDecorationExcludedDomainList verbessert, wenn lync-Benutzer Skype-Kontakte hinzufügen, die erforderlich sind, um nicht-Microsoft-Domänen zu "verzieren" identifizieren und leiten Sie Sie an Skype weiter (das Format: User (contoso. com) @MSN. com). Diese neuen Einstellungen ermöglichen die automatische Formatierung der Eingabe der Adresse des Benutzers im Dialogfeld "Skype-Kontakt hinzufügen" mit dem NameDecorationRoutingDomain (das auf MSN.com festzulegen ist), wenn es die Domänen im NameDecorationExcludedDomainList nicht enthält ( Wir können derzeit MSN.com, Live.com, hotmail.com, Outlook.com) unterstützen. 
  
3. Benutzer können nun auf einem Skype for Business-Client nach Skype-Benutzern suchen und diese hinzufügen.
    
## <a name="clients-and-interoperability-matrix"></a>Clients und Interoperabilitätsmatrix

Die folgende Tabelle umreißt die Status der Interoperabilität zwischen der jüngsten Version von Skype Consumer und der jüngsten Version von Skype for Business.
  

|**Skype-Clients**|**Hinzufügen von Kontakten, Chat, Anwesenheit, Audio und Videoanrufen**|**Kommentar**|
|:-----|:-----|:-----|
|Skype für Windows Desktop  <br/> |7.6 oder höher, Windows XP und höher  <br/> |**Neu**: Support für Windows Skype-Client unter Windows XP und Windows Vista **(erfordert neueste Client Version 7,26 oder höher)** <br/> |
|Skype Mobile – Android-Telefone und -Tablets   <br/> |6.19 oder höher unter der Betriebssystemversion Android 4.0.3 oder höher  <br/> |Geräte mit niedrigen Spezifikationen unterstützen Videoanrufe möglicherweise nicht.  <br/> |
|Skype Mobile – IOS  <br/> |6.11 oder höher, unter iOS 7 oder höher  <br/> |Nicht unterstützt werden iPhone 4 und frühere Versionen, iPod der 4. Generation und früher, iPad der 1. Generation  <br/> |
|Skype Mac  <br/> |7.19 oder höher, unter Mac OS X 10.9 (Mavericks) oder höher  <br/> |Erfordert Mac OS X 10.9 oder höher  <br/> |
|Skype Universal Windows App (Windows 10) Desktop- und Mobilgeräte  <br/> |Windows 10 (Redstone 1 oder höher)  <br/> |Die universelle Windows-App erhält im Herbst 2016 ein Update, mit dem Interop-Unterstützung hinzugefügt wird.  <br/> |
   
Die folgende Tabelle umreißt die Status der Interoperabilität zwischen der jüngsten Version von Skype for Business und der jüngsten Version von Skype Consumer.  
  
|**Client**|**Skype-Verzeichnissuche und Hinzufügen von Kontakten**|**Skype Audio/Video, Chatnachrichten-Interoperabilität**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |Ja  <br/> |Ja  <br/> |
|Skype for Business auf dem Mac  <br/> |Hinzufügen möglich (keine Suche)  <br/> |Ja  <br/> |
|Lync Desktop 2013  <br/> |Hinzufügen möglich (keine Suche)  <br/> |Ja  <br/> |
|Lync Web App – online und lokal  <br/> |-  <br/> |Nicht zutreffend  <br/> |
|Lync Mobile – Windows Phone  <br/> |In Kürze verfügbar  <br/> |Ja  <br/> |
|Lync Mobile – Android  <br/> |In Kürze verfügbar  <br/> |Ja  <br/> |
|Lync Mobile – iOS  <br/> |In Kürze verfügbar  <br/> |Ja  <br/> |
|Lync Room System  <br/> |In Kürze verfügbar  <br/> |Ja  <br/> |
|Lync Modern App (Windows 8.1)  <br/> |Ja  <br/> |Ja  <br/> |
|Lync Mac 2011  <br/> |Hinzufügen möglich (keine Suche)  <br/> |Ja  <br/> |
|Lync Desktop 2010  <br/> |Hinzufügen möglich (keine Suche)  <br/> |Ja  <br/> |
|Lync Phone Edition  <br/> |-  <br/> |Nicht zutreffend  <br/> |
|Lync Attendant  <br/> |n/v  <br/> |n/v  <br/> |
   

