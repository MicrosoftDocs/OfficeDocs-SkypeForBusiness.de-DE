---
title: Bereitstellen der Skype-Konnektivität in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Zusammenfassung: Erfahren Sie, wie Skype für Business Server 2015 mit Skype Consumer verbunden wird. Wird auch als Skype-Konnektivität bezeichnet.'
ms.openlocfilehash: 4d81d2529435d250957c775d954a33a562bed1e9
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569166"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server-2015"></a>Bereitstellen der Skype-Konnektivität in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie mehr über das Verbinden von Skype for Business Server 2015 mit Skype-Verbraucher. Wird auch als Skype-Konnektivität bezeichnet.
  
Dieser Artikel führt Sie durch die Bereitstellung für Skype-Konnektivität.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Übersicht über Skype-Konnektivität für IT-Experten

Skype-Konnektivität bietet die Möglichkeit zum Suchen nach und Hinzufügen von Skype-Benutzern Skype für Geschäftsbenutzer. Skype-Diensten ist ein Feature von Skype für Unternehmen, die Sie den Verbund und Directory Suche mit Skype-Benutzer aktivieren kann. Nachdem Sie Skype-Konnektivität aktivieren, wird Ihre Skype für Unternehmensbenutzer werden zum Suchen nach und Hinzufügen von Skype-Benutzern.
  
## <a name="skype-directory-search"></a>Skype-Verzeichnissuche

Die Funktion für die Skype-Verzeichnissuche ermöglicht Skype for Business-Benutzern, nach Skype-Kontakten zu suchen. Mit der Suchfunktion können Benutzer folgende Suchvorgänge ausführen:
  
- **Suche nach Anzeigename, Beispiel "Thorsten Scholl"** – Dadurch konnte viele Ergebnisse zurückgegeben, sodass Sie möglicherweise nicht finden, wonach Sie suchen.
    
- **Suchen nach Anzeigenamen sowie Speicherort, Beispiel "John Doe in Barcelona"** – Dadurch wird die Ergebnisse der Suche erheblich nach unten eingeschränkt.
    
- **Suchen nach e-Mails, die diesem Beispiel wird "johndoe@outlook.com"** – Dies sollte ein Ergebnis zurückgegeben werden in den meisten Fällen; diejenige, die die angegebene e-Mail-Adresse genau übereinstimmen. Aber wenn dieselbe e-Mail mehr als ein Konto zugeordnet ist, können mehrere Ergebnisse zurückgegeben werden.
    
- **Suchen nach Telefonnummer, Beispiel "123-123-1234"** – Dies sollte ein Ergebnis zurückgegeben werden in den meisten Fällen; diejenige, die die angegebene Telefonnummer genau entspricht. Telefonnummer muss die Landesvorwahl (d. h. 1-Xxx-Yyy-Zzzz) enthalten. Wenn derselben Rufnummer gibt mehr als ein Konto zugeordnet ist, können mehrere Ergebnisse zurückgegeben werden soll.
    
- **Suchen nach Skype-Name, Beispiel "JohnDoe1456"** – Wenn genaue Übereinstimmung gefunden wird, wird es als erstes Ergebnis zurückgegeben werden. Möglicherweise weiteren möglichen "name" Suchergebnisse zurückgegeben werden soll.
    
    > [!NOTE]
    > Die Suche im Skype-Verzeichnis muss in der Lage sein, mit den folgenden IP-Adressen an Port 443 zu kommunizieren: 104.40.75.246, 23.101.135.34 und 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Unterstützte Bereitstellungsmatrix für die Skype-Verzeichnissuche

In der folgenden Tabelle ist angegeben, ob die Skype-Verzeichnissuche unterstützt wird.
  

||**Skype für Business Server 2015 Front-End**|**Lync Server 2013 (oder älter) Front-End**|**Anmerkungen**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server 2015-Edgeserver  <br/> |Unterstützt  <br/> |Nicht unterstützt  <br/> |Für die Skype-Verzeichnissuche sind Skype for Business Server 2015 und Edgeserver erforderlich.  <br/> |
|Parallele Bereitstellung von Skype for Business Server 2015-Edgeserver und Lync Server 2013-Edgeserver  <br/> |Unterstützt  <br/> |Nicht unterstützt  <br/> |Der Datenverkehr der Skype-Verzeichnissuche wird über Skype for Business Server-Edgeserver verarbeitet. Der Partnerverbunddatenverkehr wird über Edgeserver verarbeitet, die vom Administrator konfiguriert wurden. Beispielsweise kann der Administrator festlegen, dass der Partnerverbunddatenverkehr weiterhin über Lync Server 2013-Edgeserver gesendet wird, die die Skype-Verzeichnissuche nicht unterstützen.  <br/> |
|Lync Server 2013-Edgeserver (oder älter)  <br/> |Nicht unterstützt  <br/> |Nicht unterstützt  <br/> ||
   
> [!NOTE]
> Der auf Skype for Business Server 2015-Front-End-Server ausgeführte Adressbuchdienst findet den 2015-Edgeserver anhand des vorhandenen Skype-Suchports 4443 im 2015 Edgeserver. 
  
> [!NOTE]
> Wenn ein Kunde in seiner lokalen Bereitstellung mehrere Standorte hat und nur ein Skype for Business Server 2015-Edgeserver/-pool bereitgestellt wurde, wird der Datenverkehr der Suche von allen Standorten über den einen verfügbaren Edgeserver verarbeitet. Der Administrator muss sicherstellen, dass die Pools aller Standorte auf den bereitgestellten Skype for Business Server 2015-Edgeserver/-pool zugreifen können. 
  
> [!NOTE]
> Der Skype-Diagrammdienst schränkt die Suchanforderungen von lokalen Kunden bzw. Office 365-Kunden ein, wenn die Anforderungsrate 15 Anforderungen pro Sekunde überschreitet. 
  
> [!NOTE]
> Für lokale Kunden in großen Unternehmen müssen die Domänen mit dem Skype-Suchdienst in die Genehmigungsliste aufgenommen werden, um höhere Anforderungsraten zuzulassen. 
  
> [!NOTE]
> Skype for Business Server 2015 unterdrückt eingehende Anforderungen, wenn sich zu viele ausstehende Anforderungen in der Warteschlange befinden. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a>Bereitstellen der Skype-Konnektivität für Skype for Business Online in Office 365

Die Skype-Konnektivität ist auch eine Funktion in Skype for Business Online, das in Office 365 enthalten ist. Sie können die Skype-Konnektivität im Skype for Business Admin Center im Office 365-Portal aktivieren.
  
Für Office 365 Midsize Business, Office 365 Enterprise, Office 365 Education und Office 365 für Behörden: Melden Sie sich beim Office 365-Portal an und öffnen Sie das Skype for Business Admin Center. Wechseln Sie zu „Externe Kommunikation“. Klicken Sie unter „Öffentliche Anbieter von Chatdiensten“ auf „Aktivieren“. Wenn Sie die einzelnen Benutzerzugriff auf Skype-Konnektivität zu steuern möchten, möchten durch einzelne Benutzer externe Kommunikation Einstellungen bearbeiten.
  
Für Office 365 Small Business Premium: Melden Sie sich bei Office 365, und wechseln Sie zu Admin \> Diensteinstellungen \> Instant messaging, Besprechungen und Konferenzen. Aktivieren Sie „Externe Kommunikation“. Der Schalter „Externe Kommunikation“ dient zum Aktivieren der Skype-Konnektivität und der Kommunikation mit anderen Unternehmen, die Skype for Business nutzen.
  
Weitere Informationen zur Skype for Business Online-Verwaltung finden Sie unter:
  
- [Lassen Sie Skype für Business Online-Benutzern die Kommunikation mit externen Skype für Business oder Skype-Kontakte](https://support.office.com/en-us/article/Let-Skype-for-Business-Online-users-communicate-with-external-Lync-or-Skype-contacts-b414873a-0059-4cd5-aea1-e5d0857dbc94?ui=en-US&amp;rs=en-US&amp;ad=US )
    
- [Lassen Sie Skype für Business Online-Benutzern außerhalb Ihrer Organisation [Small Business] kommunizieren](https://support.office.com/en-US/article/Let-Lync-Online-users-communicate-outside-your-organization-Small-Business-7F488F09-F004-4DB5-AEC5-01C262AA3D34)
    
- [Versuchen, wenn Sie Sofortnachrichten Skype für Business oder Skype externe Kontakte können nicht zu](https://support.office.com/en-us/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Verwenden Sie Skype für Unternehmen für die Verbindung mit externen Kontakten](https://support.office.com/en-US/article/Use-Lync-to-connect-with-external-contacts-E6DA21CE-FFB8-4AF3-A171-871CA245BC30)
    
- [Hinzufügen eines Kontakts in Skype für Unternehmen](https://support.office.com/en-US/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
    
- [Konfigurieren von Einstellungen für einzelne Benutzer](https://support.office.com/en-US/article/Configure-settings-for-individual-users-77B26EAC-8228-4161-BA9F-733B187BD836)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server-2015"></a>Bereitstellen der Skype-Konnektivität für Skype for Business Server 2015

Skype for Business Server 2015 nutzt die Architektur des Partnerverbundzugriffs zur Unterstützung der Konnektivität mit Skype. Dank dieser Konnektivität können Skype for Business Server-Benutzer Skype hinzufügen. Skype-Clients können ihren Kontaktlisten auch Skype for Business-Benutzer hinzufügen. Basierend auf Richtlinien, die vom Administrator festgelegt in Skype für Business Server-Benutzer über Sofortnachrichten kommunizieren können, finden Sie die Anwesenheitsinformationen des anderen und initiieren Sie Audio-und Videoanrufe zu. Die Skype-Konnektivität ist auch eine Funktion in Skype for Business Online und kann für Skype for Business Online-Kunden im Skype for Business Admin Center im Office 365-Portal aktiviert werden.
  
> [!NOTE]
> Wenn Skype for Business Server bereits für die Herstellung der Verbindung mit Windows Messenger über PIC (Public Instant Messaging Connectivity, Verbindung mit öffentlichen Chatdiensten) konfiguriert wurde, ist Ihre Bereitstellung schon für die Skype-Konnektivität konfiguriert. Als einzige Änderung sollten Sie ggf. den vorhandenen Messenger PIC-Eintrag in „Skype“ umbenennen.  
  
### <a name="accessing-the-skype-for-business-server-public-im-connectivity-provisioning-site-from-skype-for-business-server-2015"></a>Zugriff auf die Skype for Business Server-Bereitstellungswebsite für Verbindungen mit öffentlichen Chatdiensten von Skype for Business Server 2015 aus

Je nach Anzahl der Anforderungen kann es bei diesem Bereitstellungsprozess bis zu 30 Tage oder auch nur einige Tage dauern, bis er abgeschlossen ist. Wir empfehlen, diesen Prozess zuerst zu starten und dann die verbleibenden Schritte in diesem Dokument auszuführen. Nachdem der Skype-Bereitstellungsprozess für Ihr Konto abgeschlossen wurde, wird das Konto aktiviert und den entsprechend berechtigten Benutzern wird die Verbindung mit öffentlichen Chatdiensten ermöglicht.  
  
Für die Bereitstellung der Skype-Konnektivität benötigen Sie die folgenden Informationen:
  
- Die Microsoft-Vertragsnummer
    
- Den vollqualifizierten Domänenname (Fully Qualified Domain Name, FQDN) des Zugriffs-Edgediensts
    
- SIP-Domäne/n (Session Initiation Protocol)
    
- FQDNs für alle zusätzlichen Zugriffs-Edgedienste
    
- Kontaktinformationen
    
So starten Sie den Bereitstellungsprozess für die Skype-Konnektivität:
  
1. Melden Sie sich bei der Website https://pic.lync.com, mit Ihrer Microsoft Windows Live ID
    
2. Wählen Sie den Typ Ihres Microsoft-Lizenzvertrags aus.
    
3. Aktivieren Sie das Kontrollkästchen, um zu bestätigen, dass Sie die Produktbenutzungsrechte für Skype for Business Server gelesen haben und akzeptieren.
    
4. Klicken Sie auf der Seite „Initiate a Provisioning Request“ (Bereitstellungsprozess starten) auf den entsprechenden Link zum Starten eines Bereitstellungsprozesses.
    
5. Geben Sie auf der Seite Specify Provisioning Information Zugriffs-edgediensts FQDN. Zum Beispiel sip.contoso.com.
    
    > [!IMPORTANT]
    > Ab 1. Juli 2017 besteht seitens Microsoft auch die Anforderung an Kunden, den Federation DNS SRV-Eintrag für die Verbindung mit öffentlichen Chatdiensten bereitzustellen, um die weitere Funktionsfähigkeit zu sichern.  
  
6. Geben Sie mindestens einen SIP-Domänennamen ein und klicken Sie auf Hinzufügen.
    
    > [!NOTE]
    > Mindestens ein Zugriffs-Edgeserver ist erforderlich, um den Bereitstellungsprozess abzuschließen. Während ein einzelner Zugriffs-Edge-FQDN mehrere SIP-Domänen unterstützen kann, kann eine einzige SIP-Domäne nicht von mehr als einem Zugriffs-Edge-FQDN dargestellt werden. SIP-Domäne und Zugriffs-Edge-Server müssen aktiv, betriebsbereit und im Netzwerk erreichbar sein.              
  
7. Wählen Sie in der Liste der Anbieter von öffentlichen Chatdiensten den Eintrag „Skype“ aus und klicken Sie auf Weiter, um Kontaktinformationen hinzuzufügen. Senden Sie anschließend die Bereitstellungsanforderung.
    
Nachdem die Bereitstellungsanforderung gesendet wurde, kann es je nach Warteschlange bis zu 30 Tage oder auch nur einige Tage dauern, bis das Konto aktiviert ist und die Benutzer für die Skype-Konnektivität aktiviert sind.
  
### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Aktivieren von Partnerverbünden und Verbindungen mit öffentlichen Chatdiensten (PIC)

Nachdem Sie die Bereitstellungsanforderung gesendet haben, können Sie sich auf die Skype for Business Server-Umgebung und die Verwaltungsaufgaben konzentrieren, die zum Konfigurieren der Skype-Konnektivität erforderlich sind. In diesem Abschnitt wird davon ausgegangen, dass der Administrator Skype for Business Server bereitgestellt und den externen Zugriff konfiguriert hat (auch als Edgeserver bezeichnet).  
  
Es gibt drei primäre Schritte zur Aktivierung des Partnerverbunds und der PIC:
  
1. Konfigurieren des Partnerverbunds und der PIC
    
2. Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Benutzerzugriffs im Partnerverbund
    
3. Konfigurieren der Einstellung des Skype PIC-Anbieters
    
#### <a name="1-configure-federation-and-pic"></a>1. Konfigurieren des Partnerverbunds und der PIC

Der Partnerverbund ist erforderlich, damit Skype-Benutzer mit Skype for Business-Benutzern in Ihrer Organisation kommunizieren können. PIC (Public Instant Messaging Connectivity, Verbindung mit öffentlichen Chatdiensten) ist eine Partnerverbundklasse und muss konfiguriert werden, damit Skype for Business-Benutzer mit Skype-Benutzern kommunizieren können. Partnerverbund und PIC werden mit der Skype for Business Server-Systemsteuerung konfiguriert.
  
> [!NOTE]
> Der PIC-Partnerverbund wird von Live Communication Server 2005 SP1 oder Office Communications Server 2007 nicht mehr unterstützt. Zu den unterstützten Plattformen für den PIC-Partnerverbund gehören Skype for Business Server 2015, Lync Server 2013, Lync Server 2010 und Office Communications Server 2007 R2. 	 
  
Der Partnerverbund ist erforderlich, damit Skype-Benutzer mit Skype for Business-Benutzern in Ihrer Organisation kommunizieren können. PIC ist eine Partnerverbundklasse und muss konfiguriert werden, damit Skype for Business Server-Benutzer mit Skype-Benutzern kommunizieren können. Partnerverbund und PIC werden im Dialogfeld zur Edgeserverkonfiguration der Skype for Business Server-Systemsteuerung konfiguriert.
  
![Neuen Edgepool definieren](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Die Attribute „EnableSkypeIdRouting“ und „EnableSkypeDirectorySearch“ müssen in den Einstellungen für öffentliche Anbieter auf „True“ festgelegt werden (siehe Anweisungen weiter unten), um die Suche ausführen zu können. 
  
Damit sind die Verwaltungsaufgaben abgeschlossen, die auf dem Server durchgeführt werden müssen. Die Skype-Konnektivität ist nun eingerichtet.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. konfigurieren Sie mindestens eine Richtlinie zur Unterstützung der partnerbenutzerzugriff

Der Administrator muss in der Skype for Business Server-Systemsteuerung mindestens eine Richtlinie für den Zugriff externer Benutzer konfigurieren, um zu steuern, ob Skype-Benutzer mit internen Skype for Business Server-Benutzern zusammenarbeiten können.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Konfigurieren des Einstellung Skype PIC-Anbieters

Der Administrator muss in der Skype for Business Server-Verwaltungsshell die Skype for Business-Clientrichtlinie so konfigurieren, dass Skype als weiterer PIC-Anbieter angezeigt wird.  
  
> [!NOTE]
> Benutzer öffentlicher Instant Messaging-Diensten (PIC)-Dienstanbieter können nicht in Sofortnachrichten oder Konferenzen in Ihrer Organisation teilnehmen, bis Sie mindestens eine Richtlinie (Schritt 2, weiter oben in diesem Verfahren) zur Unterstützung der öffentlichen Instant Messaging-Diensten auch konfigurieren. 
  
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
    
  - IconURL: Symbol von Lync verwendet &amp; Skype für Business Client visuell identifizieren Skype-Kontakte
    
  - NameDecorationRoutingDomain und NameDecorationExcludedDomainList: Diese Einstellung ermöglicht Benutzern, Skype-Benutzer MSAs einzugeben, ohne "ergänzen" nicht von Microsoft stammenden Domänen mit "MSN" kennen. Dies entfällt die Notwendigkeit, geben Sie "Benutzer (contoso.com) @msn.com" für alle Domänen, die nicht in der ExcludedDomainList sind. Der SfB-Client formatiert automatisch das MSA, wenn die Domäne NICHT in der Excluded-Liste enthalten ist. Wir haben die am häufigsten verwendeten Microsoft Account Domänen der ausgeschlossenen Liste hinzugefügt.
    
    > [!NOTE]
    > Wenn Änderungen vorgenommen werden, müssen öffentliche Anbieter entweder und erneut hinzugefügt werden. Direkte Änderungen sind nicht zulässig. 
  
    > [!NOTE]
    > In Lync Server 2013 CU5 hinzugefügt &amp; Lync-Desktopclient in Office 2013 SP1, NameDecorationRoutingDomain und NameDecorationExcludedDomainList verbessern die Situation, auf dem Lync-Benutzer zum Hinzufügen von Skype-Kontakte erforderlich "ergänzen" nicht von Microsoft stammenden Domänen, Identifizieren und Skype weiterleiten (das Format der: user(contoso.com)@msn.com). Diese neuen Einstellungen lässt automatische Formatierung des Benutzers Adresse des Geben Sie im Dialogfeld "Skype Kontakt hinzufügen" mit der NameDecorationRoutingDomain (die zu MSN festgelegt), wenn sie keine Domänen in der NameDecorationExcludedDomainList (enthält Wir können derzeit MSN live.com, Hotmail.com, outlook.com unterstützt). 
  
3. Benutzer können nun auf einem Skype for Business-Client nach Skype-Benutzern suchen und diese hinzufügen.
    
## <a name="clients-and-interoperability-matrix"></a>Clients und Interoperabilitätsmatrix

Die folgende Tabelle umreißt die Status der Interoperabilität zwischen der jüngsten Version von Skype Consumer und der jüngsten Version von Skype for Business.
  

|**Skype-Clients**|**Hinzufügen von Kontakten, Sofortnachrichten, Anwesenheit, audio und video aufrufen**|**Kommentar**|
|:-----|:-----|:-----|
|Skype für Windows Desktop  <br/> |7.6 oder höher, Windows XP und höher  <br/> |**Neu**: Unterstützung für Windows Skype-Client für Windows XP und Windows Vista hinzugefügt ** (erfordert die neuesten Clientversion 7.26 oder höher) ** <br/> |
|Skype Mobile – Android-Telefone und -Tablets   <br/> |6.19 oder höher unter der Betriebssystemversion Android 4.0.3 oder höher  <br/> |Geräte mit niedrigen Spezifikationen unterstützen Videoanrufe möglicherweise nicht.  <br/> |
|Skype-Mobile - iOS  <br/> |6.11 oder höher, unter iOS 7 oder höher  <br/> |Nicht unterstützt werden iPhone 4 und frühere Versionen, iPod der 4. Generation und früher, iPad der 1. Generation  <br/> |
|Skype Mac  <br/> |7.19 oder höher, unter Mac OS X 10.9 (Mavericks) oder höher  <br/> |Erfordert Mac OS X 10.9 oder höher  <br/> |
|Skype Universal Windows App (Windows 10) Desktop- und Mobilgeräte  <br/> |Windows 10 (Redstone 1 oder höher)  <br/> |Die universelle Windows-App erhält im Herbst 2016 ein Update, mit dem Interop-Unterstützung hinzugefügt wird.  <br/> |
   
Die folgende Tabelle umreißt die Status der Interoperabilität zwischen der jüngsten Version von Skype for Business und der jüngsten Version von Skype Consumer.  
  
|**Client**|**Skype-Verzeichnis suchen und Hinzufügen von Kontakten**|**Skype A / V, Instant Messaging-Interop**|
|:-----|:-----|:-----|
|Skype for Business 2015  <br/> |Ja  <br/> |Ja  <br/> |
|Skype for Business auf dem Mac  <br/> |Hinzufügen möglich (keine Suche)  <br/> |Ja  <br/> |
|Lync Desktop 2013  <br/> |Hinzufügen möglich (keine Suche)  <br/> |Ja  <br/> |
|Lync Web App – online und lokal  <br/> |n/v  <br/> |n/v  <br/> |
|Lync Mobile – Windows Phone  <br/> |In Kürze verfügbar  <br/> |Ja  <br/> |
|Lync Mobile – Android  <br/> |In Kürze verfügbar  <br/> |Ja  <br/> |
|Lync Mobile – iOS  <br/> |In Kürze verfügbar  <br/> |Ja  <br/> |
|Lync Room System  <br/> |In Kürze verfügbar  <br/> |Ja  <br/> |
|Lync Modern App (Windows 8.1)  <br/> |Ja  <br/> |Ja  <br/> |
|Lync Mac 2011  <br/> |Hinzufügen möglich (keine Suche)  <br/> |Ja  <br/> |
|Lync Desktop 2010  <br/> |Hinzufügen möglich (keine Suche)  <br/> |Ja  <br/> |
|Lync Phone Edition  <br/> |-  <br/> |n/v  <br/> |
|Lync Attendant  <br/> |n/v  <br/> |n/v  <br/> |
   

