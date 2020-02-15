---
title: Bereitstellen und Konfigurieren der Mobilität für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: In diesem Artikel werden Sie schrittweise durch die Schritte zum Konfigurieren einer vorhandenen Skype for Business Server Installation für die Verwendung des mobilitätsdiensts geleitet, sodass Ihre mobilen Geräte Skype for Business Server Mobilitätsfunktionen nutzen können.
ms.openlocfilehash: 457eeff39c87f20326d64cc5227745b43e0af5f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029066"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Bereitstellen und Konfigurieren der Mobilität für Skype for Business Server  
 
In diesem Artikel werden Sie schrittweise durch die Schritte zum Konfigurieren einer vorhandenen Skype for Business Server Installation für die Verwendung des mobilitätsdiensts geleitet, sodass Ihre mobilen Geräte Skype for Business Server Mobilitätsfunktionen nutzen können.
  
Nachdem Sie den [Mobilitäts Plan für Skype for Business Server](../plan-your-deployment/mobility.md) Artikel überprüft haben, sollten Sie bereit sein, mit den folgenden Schritten fortzufahren, um die Mobilität in Ihrer Skype for Business Server Umgebung bereitzustellen. Die Schritte sind wie folgt (und in dieser Tabelle ist eine Berechtigungsliste eingeschlossen):
  
|**Phase**|**Berechtigungen**|
|:-----|:-----|
|[Erstellen von DNS-Einträgen](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Domänen-Admins  <br/> DnsAdmins  <br/> |
|[Ändern von Zertifikaten](deploy-and-configure-mobility.md#ModCerts) <br/> |Lokaler Administrator  <br/> |
|[Konfigurieren des Reverseproxys](deploy-and-configure-mobility.md#ConfigRP) <br/> |Lokaler Administrator  <br/> |
|[Konfigurieren der AutoErmittlung für Mobilität mit hybridbereitstellungen](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domänen-Admins  <br/> |
|[Testen der Mobilitätsbereitstellung](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[Konfigurieren von Pushbenachrichtigungen](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[Konfigurieren der Mobilitätsrichtlinie](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
Alle folgenden Abschnitte enthalten Schritte, die davon ausgehen, dass Sie das Planungsthema gelesen haben. Wenn irgendetwas verwirrend ist, können Sie sich die Informationen dort ansehen.

> [!NOTE]
> MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung. Alle aktuellen Skype for Business mobilen Clients verwenden bereits Unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit älteren Clients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.
  
## <a name="create-dns-records"></a>Erstellen von DNS-Einträgen
<a name="CreateDNSRec"> </a>

Sie verfügen möglicherweise bereits über diese als Teil Ihrer Skype for Business Server Umgebung, aber Sie müssen die folgenden Einträge erstellen, damit AutoDiscovery funktioniert:
  
- Ein interner DNS-Eintrag zur Unterstützung mobiler Benutzer, die im Netzwerk Ihrer Organisation eine Verbindung herstellen.
    
- Ein externer (oder öffentlicher) DNS-Eintrag zur Unterstützung mobiler Benutzer, die von außerhalb des Netzwerks Ihrer Organisation eine Verbindung herstellen.
    
Bei diesen Einträgen kann es sich entweder um einen (Host-) Namen oder um CNAME-Einträge handeln (Sie müssen nicht beides machen, sondern nur die Schritte für alle hier).
  
### <a name="create-an-internal-dns-cname-record"></a>Erstellen eines internen DNS-CNAME-Eintrags

1. Melden Sie sich bei einem DNS-Server in Ihrem Netzwerk an, der entweder Mitglied der Gruppe " **Domänen-Admins** " oder " **DnsAdmins** " ist.
    
2. Klicken Sie auf **Start**, wählen Sie **Verwaltungs Tools** aus (möglicherweise müssen Sie danach **Suchen** , wenn keine Option im Startmenü angezeigt wird), und klicken Sie dann auf **DNS** , um das DNS-Verwaltungs-Snap-in zu öffnen.
    
3. Im linken Bereich des Konsolenfensters müssen Sie zur Domäne wechseln, in der sich die Front-End-Server Ihrer Skype for Business Server befinden, und die **Forward-Lookupzonen** dort erweitern.
    
4. Nehmen Sie sich einen Moment Zeit, um zu sehen, welche der folgenden Sie haben:
    
   - Alle Host-A-oder AAAA-Einträge für Ihre Front-End-Server (Standard oder Enterprise) oder Front-End-Pool (s).
    
   - Beliebige Host-a-oder AAAA-Einträge für einen Director oder Directorpool (eine optionale Konfiguration, die Sie in Ihrer Bereitstellung möglicherweise haben).
    
5. Nachdem Sie dies festgestellt haben, klicken Sie mit der rechten Maustaste auf den SIP-Domänennamen, und wählen Sie dann im Menü **Neuer Alias (CNAME)** aus.
    
6. Geben Sie "lyncdiscoverinternal" für den Hostnamen für die interne URL des AutoErmittlungsdiensts in das Textfeld **Alias Name** ein.
    
7. Im **vollqualifizierten Domänennamen (FQDN für den Zielhost**müssen Sie den internen Webdienste-FQDN für Ihre Front-End-Pool (oder eine einzelne Front-End-Server oder Directorpool oder Director) eingeben oder durchsuchen, die in Schritt 4 oben identifiziert wurde. Klicken Sie auf OK, wenn diese eingegeben wird.
    
8. Sie müssen einen neuen CNAME-Eintrag für die AutoErmittlung in der Forward-Lookupzone für jede SIP-Domäne erstellen, die in Ihrer Skype for Business Server Umgebung unterstützt wird.
    
### <a name="create-an-external-dns-cname-record"></a>Erstellen eines externen DNS-CNAME-Eintrags

1. Diese Schritte sind generisch, da wir nicht feststellen können, welchen öffentlichen DNS-Anbieter Sie möglicherweise verwenden, aber wir möchten Ihnen dennoch weiterhelfen. Melden Sie sich bei Ihrem öffentlichen DNS-Anbieter mit einem Konto an, das dort neue DNS-Einträge erstellen kann.
    
2. Zu diesem Zeitpunkt sollte für Skype for Business Server bereits eine SIP-Domäne vorhanden sein. Erweitern Sie die **Forward-Lookupzone** für diese SIP-Domäne, oder öffnen Sie Sie andernfalls.
    
3. Nehmen Sie sich einen Moment Zeit, um zu sehen, welche der folgenden Sie haben:
    
   - Alle Host-A-oder AAAA-Einträge für Ihre Front-End-Server (Standard oder Enterprise) oder Front-End-Pool (s).
    
   - Beliebige Host-a-oder AAAA-Einträge für einen Director oder Directorpool (eine optionale Konfiguration, die Sie in Ihrer Bereitstellung möglicherweise haben).
    
4. Sobald Sie über diese Informationen verfügen, sollten Sie in der Lage sein, eine Option zum Erstellen eines **neuen Alias (CNAME)** auszuwählen.
    
5. Nun sollten Sie in der Lage sein, einen **Alias Namen**einzugeben, müssen Sie hier lyncdiscover für die externe AutoErmittlungsdienst-URL eingeben.
    
6. Als nächstes sollte ein Bereich in einen **FQDN für den Zielhost**eingegeben werden, dies muss der FQDN für Ihre Front-End-Pool (oder einzelne Front-End-Server oder Directorpool oder Director) sein, die in Schritt 3 oben identifiziert wird.
    
7. Sie müssen möglicherweise hier speichern, oder wenn Sie zusätzliche CNAME-Einträge in der Forward-Lookupzone jeder SIP-Domäne in Ihrer Skype for Business Server-Umgebung erstellen müssen, sollten Sie dies tun, aber wenn Sie bereit sind, speichern Sie Ihre Arbeit.
    
### <a name="create-an-internal-dns-a-record"></a>Erstellen eines internen DNS-A-Eintrags

1. Melden Sie sich bei einem DNS-Server in Ihrem Netzwerk an, der entweder Mitglied der Gruppe " **Domänen-Admins** " oder " **DnsAdmins** " ist.
    
2. Klicken Sie auf **Start**, wählen Sie **Verwaltungs Tools** aus (möglicherweise müssen Sie danach **Suchen** , wenn keine Option im Startmenü angezeigt wird), und klicken Sie dann auf **DNS** , um das DNS-Verwaltungs-Snap-in zu öffnen.
    
3. Im linken Bereich des Konsolenfensters müssen Sie zur Domäne wechseln, in der sich die Front-End-Server Ihrer Skype for Business Server befinden, und die **Forward-Lookupzonen** dort erweitern.
    
4. Nehmen Sie sich einen Moment Zeit, um zu sehen, welche der folgenden Sie haben:
    
   - Alle Host-A-oder AAAA-Einträge für Ihre Front-End-Server (Standard oder Enterprise) oder Front-End-Pool (s).
    
   - Beliebige Host-a-oder AAAA-Einträge für einen Director oder Directorpool (eine optionale Konfiguration, die Sie in Ihrer Bereitstellung möglicherweise haben).
    
5. Nachdem Sie dies festgestellt haben, klicken Sie mit der rechten Maustaste auf den SIP-Domänennamen, und wählen Sie dann im Menü **neue Host (A oder AAAA)** aus.
    
6. Geben Sie im Textfeld **Name den Namen** "lyncdiscoverinternal" für den Hostnamen für die interne URL des AutoErmittlungsdiensts ein.
    
7. Geben Sie in das Textfeld **IP-Adresse** die interne Webdienste-IP-Adresse für Ihre Front-End-Pool ein (oder eine einzelne Front-End-Server oder Directorpool oder Director), die in Schritt 4 oben identifiziert wurde.
    
8. Klicken Sie anschließend auf **Host hinzufügen**, und klicken Sie dann auf **OK**.
    
9. Sie müssen eine neue autodiscover a-oder AAAA-Einträge in der Forward-Lookupzone für jede SIP-Domäne erstellen, die in Ihrer Skype for Business Server Umgebung unterstützt wird. Wiederholen Sie dazu die Schritte 6-8 so oft wie nötig.
    
10. Wenn Sie fertig sind, klicken Sie auf **Fertig**.
    
### <a name="create-an-external-dns-a-record"></a>Erstellen eines externen DNS-A-Eintrags

1. Diese Schritte sind generisch, da wir nicht feststellen können, welchen öffentlichen DNS-Anbieter Sie möglicherweise verwenden, aber wir möchten Ihnen dennoch weiterhelfen. Melden Sie sich bei Ihrem öffentlichen DNS-Anbieter mit einem Konto an, das dort neue DNS-Einträge erstellen kann.
    
2. Zu diesem Zeitpunkt sollte für Skype for Business Server bereits eine SIP-Domäne vorhanden sein. Erweitern Sie die **Forward-Lookupzone** für diese SIP-Domäne, oder öffnen Sie Sie andernfalls.
    
3. Nehmen Sie sich einen Moment Zeit, um zu sehen, welche der folgenden Sie haben:
    
   - Alle Host-A-oder AAAA-Einträge für Ihre Front-End-Server (Standard oder Enterprise) oder Front-End-Pool (s).
    
   - Beliebige Host-a-oder AAAA-Einträge für einen Director oder Directorpool (eine optionale Konfiguration, die Sie in Ihrer Bereitstellung möglicherweise haben).
    
4. Sobald Sie diese Informationen haben, sollten Sie in der Lage sein, eine Option zum Erstellen eines **neuen Hosts a oder AAAA**auszuwählen.
    
5. Nun sollten Sie in der Lage sein, einen **Namen**einzugeben, müssen Sie hier lyncdiscover für die externe AutoErmittlungsdienst-URL eingeben.
    
6. Als nächstes sollte ein Bereich in einer **IP-Adresse**eingegeben werden, dies muss die IP für Ihre Front-End-Pool (oder einzelne Front-End-Server oder Directorpool oder Director) sein, die in Schritt 3 oben identifiziert wird.
    
7. Sie müssen möglicherweise hier speichern, oder wenn Sie zusätzliche A-oder AAAA-Einträge in der Forward-Lookupzone jeder SIP-Domäne für Ihre Skype for Business Server Umgebung erstellen müssen, sollten Sie dies tun, aber wenn Sie bereit sind, speichern Sie Ihre Arbeit.
    
## <a name="modify-certificates"></a>Ändern von Zertifikaten
<a name="ModCerts"> </a>

Wenn Sie Fragen zur Planung von Zertifikaten haben, haben wir dies in unserem [Mobilitäts Plan für Skype for Business Server](../plan-your-deployment/mobility.md) Artikel dokumentiert. Nachdem Sie das überprüft haben, führen wir Sie durch die folgenden Schritte:
  
- Benötige ich neue Zertifikate?
    
- Anfordern neuer Zertifikate von Ihrer Zertifizierungsstelle (Certification Authority, ca).
    
- Aktualisieren Ihrer in-Place-Zertifikate mit den ersetzen mit PowerShell.
    
- Überprüfen der Zertifikate mithilfe des Zertifikat-Snap-Ins in der Microsoft Management Console (MMC).
    
### <a name="do-i-need-new-certificates"></a>Benötige ich neue Zertifikate?

1. Zunächst müssen Sie möglicherweise überprüfen, welche Zertifikate in-Place sind und ob Sie über die erforderlichen Einträge verfügen. Hierzu müssen Sie sich bei Ihrem Skype for Business Server mit einem Konto anmelden, das ein lokaler Administrator ist. Dieses Konto muss für einige dieser Schritte möglicherweise auch über Rechte an der Zertifizierungsstelle (Certification Authority, ca) verfügen.
    
2. Öffnen Sie die Skype for Business Server-Verwaltungsshell (Sie können die Suche verwenden, um Sie zu finden, wenn Sie nicht an das Startmenü oder die Taskleiste angeheftet ist).
    
3. Es wird wichtig sein, dass Sie wissen, welche Zertifikate zugewiesen wurden, bevor Sie versuchen, ein aktualisiertes Zertifikat hinzuzufügen. Geben Sie also an der Befehlszeile Folgendes ein:
    
   ```powershell
   Get-CsCertificate
   ```

4. Die Informationen aus Schritt 3 sind für Sie eindeutig. Sie müssen überprüfen, ob Sie ein einzelnes Zertifikat haben, das für mehrere Dinge zugewiesen wurde, oder ob für die verschiedenen Komponenten, die Sie benötigen, ein anderes Zertifikat zugewiesen ist. Mit dem Parameter **use** erfahren Sie, wie ein Zertifikat verwendet wird, und mit dem Parameter **Fingerabdruck** erfahren Sie, ob es sich um dasselbe Zertifikat oder mehrere certs handelt.
    
5. Wenn Sie die San-Einträge in unserem Planungsabschnitt empfohlen haben, sind Sie gut. Wenn dies nicht der Fall ist, müssen Sie ein neues Zertifikat oder mehrere Zertifikate (je nach Konfiguration) von Ihrer Zertifizierungsstelle anfordern.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>Anfordern eines neuen Zertifikats oder von Zertifikaten von Ihrer Zertifizierungsstelle (Certification Authority, ca)

1. Nachdem Sie überprüft haben, welche San-Einträge vorhanden sind, wissen Sie, dass Sie über ein **einzelnes Zertifikat** verfügen (nachdem Sie die obigen Schritte überprüft haben), und Sie haben gelernt, dass Sie nicht über alle benötigten Einträge verfügen. Es muss eine neue Zertifikatanforderung an Ihre Zertifizierungsstelle gestellt werden. Öffnen Sie die Skype for Business Server PowerShell:
    
   - Für ein fehlendes AutoErmittlungsdienst-San (Ersetzen des-ca-Parameters durch ihren eigenen Pfad der Zertifizierungsstelle):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Wenn Sie nun über mehrere SIP-Domänen verfügen, können Sie den AllSipDomain-Parameter nicht wie im obigen Beispiel verwenden. Sie müssen stattdessen den Parameter Domain Name verwenden. Wenn Sie den Parameter Domain Name verwenden, müssen Sie den FQDN für die "lyncdiscoverinternal"-und lyncdiscover-Datensätze definieren. Ein Beispiel wäre (Ersetzen des-ca-Parameters durch ihren eigenen Pfad der Zertifizierungsstelle):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. Oder nachdem Sie überprüft haben, welche San-Einträge vorhanden sind, haben Sie festgestellt, dass Sie über **mehrere Zertifikate** verfügen, die nicht über alle benötigten Einträge verfügen. Es muss eine neue Zertifikatanforderung an Ihre Zertifizierungsstelle gestellt werden. Öffnen Sie die Skype for Business Server PowerShell:
    
   - Für ein fehlendes AutoErmittlungsdienst-San (Ersetzen des-ca-Parameters durch ihren eigenen Pfad der Zertifizierungsstelle):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Wenn Sie nun über mehrere SIP-Domänen verfügen, können Sie den AllSipDomain-Parameter nicht wie im obigen Beispiel verwenden. Sie müssen stattdessen den Parameter Domain Name verwenden. Wenn Sie den Parameter Domain Name verwenden, müssen Sie den FQDN für die "lyncdiscoverinternal"-und lyncdiscover-Datensätze definieren. Beispiele wären (Ersetzen des-ca-Parameters durch ihren eigenen Pfad der Zertifizierungsstelle):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - Nachdem die neuen Zertifikate von der Zertifizierungsstelle generiert wurden, müssen Sie Sie zuweisen.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Zuweisen von Zertifikaten mithilfe Skype for Business Server Verwaltungsshell

- Je nachdem, was Sie im Abschnitt Ich benötige neue Zertifizierungen gefunden haben, müssen Sie **eine** der folgenden Aktionen ausführen.
    
  - Wenn Sie ein einzelnes Zertifikat für alles haben (die Fingerabdrücke sind identisch), müssen Sie Folgendes ausführen:
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - Wenn Sie unterschiedliche Zertifikate für Dinge haben (die Fingerabdrücke sind alle unterschiedlich), führen Sie diese stattdessen aus:
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Anzeigen von Zertifikaten in der Microsoft Management Console (MMC)

1. Sie haben die Möglichkeit, ihre Zertifikate mit dem Zertifikat-Snap-in für die MMC zu betrachten. Geben Sie einfach MMC in die Suche ein, und es sollte als Anwendungsoption angezeigt werden.
    
2. Um das Zertifikat-Snap-in hinzuzufügen, müssen Sie auf **Datei**und dann auf **Snap-in hinzufügen/entfernen klicken...** (oder Tastenkombination **STRG + M** wäre auch möglich). **Zertifikate** sind eine Option im linken Bereich, wählen Sie Sie aus, und klicken Sie dann im Popupfenster auf **Computer Konto** und dann auf **weiter**.
    
3. Immer noch im Popupfenster, aller Wahrscheinlichkeit nach tun Sie dies auf dem Computer, der zu den Zertifikaten gehört, die Sie sich ansehen müssen, also lassen Sie die Auswahl auf dem **lokalen Computer** , wenn das so ist. Wenn Sie auf einem Remotecomputer arbeiten, ändern Sie das Optionsfeld auf **einen anderen Computer** , und geben Sie dann entweder den FQDN des Computers ein, oder verwenden Sie die Schaltfläche **Durchsuchen** , um nach diesem Computer über AD zu suchen. Nachdem Sie den Computer ausgewählt haben, müssen Sie auf **Fertig stellen** und dann auf **OK** klicken, um das Snap-in zur MMC hinzuzufügen.
    
4. Erweitern Sie den Abschnitt **Zertifikate** im linken Bereich der MMC. Erweitern Sie außerdem den **persönlichen** Ordner, und wählen Sie dann **Zertifikate**aus. Auf diese Weise können Sie die Zertifikate in diesem Speicher anzeigen.
    
5. Sie müssen das Zertifikat suchen, das Sie anzeigen möchten, klicken Sie mit der rechten Maustaste darauf, und wählen Sie dann **Öffnen**aus.
    
    > [!NOTE]
    > Woher wissen Sie, welches Zertifikat das ist? Es sollte sich entweder um das einzelne Zertifikat handeln, das für Ihre Farm zugewiesen wurde, oder Sie können mehrere Zertifikate für verschiedene Dinge wie Standard, interne Webdienste usw. haben, in diesem Fall müssen Sie möglicherweise mehrere Zertifikate betrachten. Mehrere Zertifikate haben denselben Fingerabdruck. 
  
6. Nachdem Sie die **Zertifikat** Ansicht erreicht haben, wählen Sie **Details**aus. Auf diese Weise können Sie den Zertifikatantragstellernamen anzeigen, wenn Sie den **Betreff**auswählen, und der zugewiesene Antragstellername und die zugehörigen Eigenschaften werden angezeigt.
    
7. Sie müssen auch die **alternativen Antragstellernamen** -Einträge überprüfen. Sie können eine oder mehrere der folgenden Informationen finden:
    
   - Der Poolname für diesen Pool oder der Name des einzelnen Servers, wenn es sich nicht um einen Pool handelt.
    
   - Der Servername, dem das Zertifikat zugewiesen ist.
    
   - Einfache URL-Einträge, in der Regel Meet und dialin.
    
   - Webdienste interner und Webdienste externer Namen (beispielsweise webpool01.contoso.net, webpool01.contoso.com) basierend auf den im Topologie-Generator vorgenommenen Entscheidungen und übermäßig berittenen Webdienste Auswahlen.
    
   - Wenn bereits zugewiesen, lyncdiscover. \<sipdomain "\> und" lyncdiscoverinternal ". \<sipdomain "\> -Datensätze.
    
     Sie müssen mehrere Zertifikate überprüfen, wenn Sie mehr als einen zugewiesenen haben (überprüfen Sie den obigen Hinweis).
    
8. Wenn Sie also lyncdiscover finden. \<sipdomain "\> und" lyncdiscoverinternal ". \<sipdomain "\> -Datensätze, Sie haben diese bereits konfiguriert. Sie können die MMC schließen.
    
9. Wenn Sie nicht zugewiesen sind, müssen Sie entweder eine neue Zertifikatanforderung erstellen (siehe oben), oder Sie müssen Sie nach der Anforderung installieren (es wird empfohlen, dass Sie die oben beschriebene PowerShell weiter oben ausführen).
    
## <a name="configure-the-reverse-proxy"></a>Konfigurieren des Reverseproxys
<a name="ConfigRP"> </a>

Die folgenden Schritte sind nicht genau zu befolgen. Das liegt daran, dass wir Sie in früheren Versionen des Produkts durchlaufen haben, beispielsweisedurch die Konfiguration von Threat Management Gateway (TMG) und wenn Sie das nicht verwenden, müssen Sie Ihre eigene Version von dort aus bearbeiten.
  
TMG wird von Microsoft nicht mehr als Produkt angeboten, und wenn Sie es noch konfigurieren müssen, können Sie sich die [lync Server 2013 Schritte](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx)ansehen. Die folgenden Informationen sollten jedoch allgemein hilfreich sein, auch wenn es nicht möglich ist, spezifische Exemplarische Vorgehensweisen für jeden Reverseproxy bereitzustellen.
  
Es gibt zwei wichtige Punkte zu beachten:
  
- Werden Sie Ihre anfängliche Auto Ermittlungsanforderung über HTTPS ausführen (was wir empfehlen)?
    
  - Wenn Sie über eine Webveröffentlichungsregel verfügen, müssen Sie Sie ändern.
    
  - Wenn Sie noch nicht über eine Webveröffentlichungsregel verfügen, müssen Sie Sie erstellen.
    
- Wenn Sie Ihre anfängliche Auto Ermittlungsanforderung über HTTP ausführen, müssen Sie auch diese Regel erstellen oder ändern.
    
> [!NOTE]
> **Wichtiger Hinweis** Ein Proxy Timeoutwert ist eine Zahl, die von der Bereitstellung bis zur Bereitstellung variieren kann. Sie sollten Ihre Bereitstellung überwachen und den Wert für die beste Benutzerfreundlichkeit für Clients ändern. Möglicherweise können Sie den Wert so niedrig wie 200 festlegen. Wenn Sie lync Mobile-Clients in Ihrer Umgebung unterstützen, sollten Sie den Wert auf 960 festlegen, um Timeouts für Push-Benachrichtigungen von Office 365 zu ermöglichen, die einen Timeoutwert von 900 haben. Es ist sehr wahrscheinlich, dass Sie den Timeoutwert verbessern müssen, um zu vermeiden, dass der Client die Verbindung trennt, wenn der Wert zu niedrig ist, oder die Zahl verringern, wenn Verbindungen über den Proxy nicht getrennt, aber nach dem Trennen des Clients gelöscht werden. Überwachung und Baselining was in Ihrer Umgebung üblich ist, ist die einzig genaue Möglichkeit, die entsprechende Einstellung für diesen Wert zu ermitteln.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Ändern der vorhandenen Webveröffentlichungsregel für das externe autodiscover-San und die URL

1. Öffnen Sie die Reverse-Proxyschnittstelle.
    
2. Sie müssen die Webveröffentlichungsregel suchen und die Option Bearbeiten auswählen (je nach Konfiguration des Reverse-Proxys ist Sie möglicherweise in einem Menü oder einer Registerkarte).
    
3. Es sollte ein Bereich vorhanden sein, der angibt, auf welche Webveröffentlichungsregel angewendet wird. Sie müssen diese Regel für eingehende Websites oder Anforderungen für Websites ändern. Sie werden einen neuen Eintrag **Hinzufügen** .
    
4. Geben Sie den Namen der Auto Ermittlungs Website ein (das Beispiel wird lyncdiscover.contoso.com verwendet), und klicken Sie je nach Format des Reverse-Proxys auf **OK** oder **Speichern**.
    
5. Möglicherweise verfügen Sie über ein neues Zertifikat, das den San-Eintrag der AutoErmittlung enthält. Diese muss ebenfalls installiert und für die Verwendung entsprechend den Einstellungen des Reverse-Proxys konfiguriert werden. Achten Sie darauf, alles zu speichern, wenn die Konfiguration abgeschlossen ist.
    
6. Wenn Ihr Reverseproxy über eine **Test** Funktionalität verfügt, verwenden Sie ihn, um sicherzustellen, dass alles ordnungsgemäß funktioniert.
    
7. Möglicherweise müssen Sie diese Schritte jetzt wiederholen, wenn Sie einen Director oder Directorpool in Ihrer Umgebung haben (Dies würde bedeuten, dass Sie eine zweite Regel haben).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Erstellen einer Webveröffentlichungsregel für die externe Auto Ermittlungs-URL

1. Öffnen Sie die Reverse-Proxyschnittstelle.
    
2. Sie müssen herausfinden, wo in der Schnittstelle Sie Ihre Webveröffentlichungsregeln erstellen, und die Option **neu** oder **Erstellen** auswählen (je nach Konfiguration des Reverse-Proxys kann es sich um ein Menü oder eine Registerkarte handeln). Sie benötigen die Option zum Erstellen einer neuen Webveröffentlichungsregel.
    
3. In der Regel müssen Sie die folgenden Informationen eingeben:
    
   - **Name**: der Name für die Regel
    
   - **Regelaktion**: in diesem Fall handelt es sich um eine **Zulassungs** Regel, Sie lassen etwas durch ihren Reverseproxy passieren.
    
   - Die **Veröffentlichungs** Regel oder Option, die Sie auswählen, wäre die **einzelne Website oder das Lastenausgleichsmodul**.
    
   - Dies muss **SSL** für den externen Zugriff sein, wählen Sie diese Option aus.
    
   - Sie müssen einen Pfad für die **interne Veröffentlichung**veröffentlichen und den FQDN für die externe Webdienste auf dem Lastenausgleichsmodul Ihres Front-End-Pool (oder den FQDN des Lastenausgleichs für das Directorpool, wenn Sie einen haben), ein Beispiel wäre sfb_pool01. contoso. local geben.
    
   - Sie sollten * ** / **als den zu veröffentlichenden Pfad eingeben, aber Sie müssen auch **den ursprünglichen Hostheader weiterleiten**.
    
   - Es wird eine Option für **öffentliche oder externe Namen** Details oder Informationen geben. An dieser Stelle können Sie Folgendes eingeben:
    
   - **Akzeptieren von Anforderungen**, sollte jedoch für den Domänennamengelten.
    
   - Für den **Namen**sollten Sie lyncdiscover eingeben **.** <sipdomain>(Dies ist die externe AutoErmittlungsdienst-URL). Wenn Sie nun eine Regel für die externe Webdienste-URL auf dem Front-End-Pool erstellen, müssen Sie den FQDN für die externe Webdienste auf dem Front-End-Pool eingeben (beispielsweise lyncwebextpool01.contoso.com).
    
   - Es wird eine **Pfad** Option geben, und Sie müssen * hier eingeben ** / **.
    
   - Sie müssen einen **SSL-Listener** mit Ihrem aktuellen öffentlichen Zertifikat auswählen.
    
   - Die **Authentifizierungsdelegierung** sollte auf **keine Delegierung**festgelegt werden, aber direkte Clientauthentifizierung **sollte** zulässig sein.
    
   - Die Regel sollte auf **alle Benutzer**festgelegt werden.
    
   - Dies sollten alle Informationen sein, die Sie zum Erstellen dieser Regel benötigen, damit Sie fortfahren können.
    
4. Sie müssen sicherstellen, dass der **ursprüngliche Hostheader** weitergeleitet wird.
    
5. Die **Webserver-** Ports müssen ebenfalls festgelegt werden, Sie müssen folgende Schritte ausführen:
    
   - **Umleiten von Anforderungen an den HTTP-Port** und die Portnummer sollten **8080**sein.
    
   - **Umleiten von Anforderungen an SSL-Port** und die Portnummer sollten **4443**sein.
    
6. Wenn alles konfiguriert ist, müssen Sie diese speichern oder anwenden, und dann möchten Sie die Regel testen.
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>Erstellen einer Webveröffentlichungsregel für Port 80 (optional)

1. Öffnen Sie die Reverse-Proxyschnittstelle.
    
2. Sie müssen herausfinden, wo in der Schnittstelle Sie Ihre Webveröffentlichungsregeln erstellen, und die Option **neu** oder **Erstellen** auswählen (je nach Konfiguration des Reverse-Proxys kann es sich um ein Menü oder eine Registerkarte handeln). Sie benötigen die Option zum Erstellen einer neuen Webveröffentlichungsregel.
    
3. In der Regel müssen Sie die folgenden Informationen eingeben:
    
   - **Name**: der Name für die Regel
    
   - **Regelaktion**: in diesem Fall handelt es sich um eine **Zulassungs** Regel, Sie lassen etwas durch ihren Reverseproxy passieren.
    
   - Die **Veröffentlichungs** Regel oder Option, die Sie auswählen, wäre die **einzelne Website oder das Lastenausgleichsmodul**.
    
   - Hierbei muss es sich um eine nicht gesicherte Verbindung handeln, um eine **Verbindung mit dem veröffentlichten Webserver oder der Farm herzustellen**.
    
   - Sie müssen einen Pfad für die **interne Veröffentlichung**veröffentlichen und den FQDN für die **VIP-Adresse** des Lastenausgleichs für Ihre Front-End-Pool eingeben, beispielsweise sfb_pool01. contoso. local.
    
   - Sie sollten * ** / **als den zu veröffentlichenden Pfad eingeben, aber Sie müssen auch **den ursprünglichen Hostheader weiterleiten**.
    
   - Es wird eine Option für **öffentliche oder externe Namen** Details oder Informationen geben. An dieser Stelle können Sie Folgendes eingeben:
    
   - **Akzeptieren von Anforderungen**, sollte jedoch für den Domänennamengelten.
    
   - Für den **Namen**sollten Sie lyncdiscover eingeben **.** <sipdomain>(Dies ist die externe AutoErmittlungsdienst-URL).
    
   - Es wird eine **Pfad** Option geben, und Sie müssen * hier eingeben ** / **.
    
   - Sie müssen einen Weblistener auswählen oder Ihrem Reverseproxy erlauben, einen zu erstellen.
    
   - Die **Authentifizierungsdelegierung** sollte auf **keine Delegierung**festgelegt werden, die direkte Clientauthentifizierung **sollte jedoch nicht** zulässig sein.
    
   - Die Regel sollte auf **alle Benutzer**festgelegt werden.
    
   - Dies sollten alle Informationen sein, die Sie zum Erstellen dieser Regel benötigen, damit Sie fortfahren können.
    
4. Die **Webserver-** Ports müssen festgelegt werden, Sie müssen folgende Schritte ausführen:
    
   - **Umleiten von Anforderungen an den HTTP-Port** und die Portnummer sollten **8080**sein.
    
   - **Umleiten von Anforderungen an SSL-Port** und die Portnummer sollten **4443**sein.
    
5. Wenn alles konfiguriert ist, müssen Sie diese speichern oder anwenden, und dann möchten Sie die Regel testen.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Konfigurieren der AutoErmittlung für Mobilität mit hybridbereitstellungen
<a name="ConfigAutoD"> </a>

Hybrid Umgebungen in Skype for Business Server sind Umgebungen, in denen eine lokale und O365 Umgebung kombiniert wird. Wenn Sie Skype for Business Server in einer Hybrid Umgebung arbeiten, muss der AutoErmittlungsdienst in der Lage sein, einen Benutzer aus einer dieser Umgebungen zu finden.
  
Damit Mobile Clients ermitteln können, wo sich ein Benutzer befindet, muss der AutoErmittlungsdienst mit einer neuen URL (Uniform Resource Locator) konfiguriert werden. Das sind die Schritte:
  
1. Öffnen Sie Skype for Business Server Management Shell.
    
2. Führen Sie Folgendes aus, um den Wert des Attributs **ProxyFQDN** für Ihre Skype for Business Server Umgebung abzurufen:
    
   ```powershell
   Get-CsHostingProvider
   ```

3. Führen Sie dann noch im Fenster Shell folgendes aus:
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    Dabei wird [Identity] durch den Domänennamen des freigegebenen SIP-Adressraums ersetzt.
    
## <a name="test-your-mobility-deployment"></a>Testen der Mobilitätsbereitstellung
<a name="TestMobility"> </a>

Nachdem Sie Skype for Business Server Mobilitätsdienst und Skype for Business Server AutoErmittlungsdienst bereitgestellt haben, sollten Sie eine Testtransaktion ausführen, um sicherzustellen, dass die Bereitstellung richtig funktioniert. Sie können **Test-CsUcwaConference** ausführen, um die Fähigkeit von zwei Benutzern zu testen, um eine Konferenz zu erstellen, zu verbinden und zu kommunizieren. Sie benötigen zwei Benutzer (Real oder Test) und die vollständigen Anmeldeinformationen, um diese Tests durchführen zu können. Dieser Befehl funktioniert sowohl für Skype for Business-als auch für lync Server 2013-Clients.
  
Für lync Server 2010 Clients in Skype for Business Server 2015 müssen Sie **Test-CsMcxP2PIM** ausführen, um zu testen. Ihre lync Server 2010 Benutzer müssen weiterhin tatsächliche Benutzer oder vordefinierte Testbenutzer sein, und Sie benötigen Ihre Kennwortanmeldeinformationen.

> [!NOTE]
> MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung. Alle aktuellen Skype for Business mobilen Clients verwenden bereits Unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit älteren Clients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Testen von Konferenzen für Skype for Business und lync 2013 Mobile Clients

1. Melden Sie sich als Mitglied der **CsAdministrator** -Rolle auf einem beliebigen Computer an, auf dem **Skype for Business Server Management Shell** und **OCSCore** installiert sind.
    
2. Starten Sie die **Skype for Business Server-Verwaltungsshell** (Sie können den Namen in "suchen" eingeben oder zu " **Alle Programme** " wechseln und ihn auswählen).
    
3. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   Es ist auch möglich, Anmeldeinformationen in einem Skript festzulegen und an das Test-Cmdlet zu übergeben. Ein Beispiel hierfür finden Sie unten.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Testen von Konferenzen für lync 2010 Mobile Clients

> [!NOTE]
> MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung. Alle aktuellen Skype for Business mobilen Clients verwenden bereits Unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit älteren Clients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.

1. Melden Sie sich als Mitglied der **CsAdministrator** -Rolle auf einem beliebigen Computer an, auf dem **Skype for Business Server Management Shell** und **OCSCore** installiert sind.
    
2. Starten Sie die **Skype for Business Server-Verwaltungsshell** (Sie können den Namen in "suchen" eingeben oder zu " **Alle Programme** " wechseln und ihn auswählen).
    
3. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   Es ist auch möglich, Anmeldeinformationen in einem Skript festzulegen und an das Test-Cmdlet zu übergeben. Ein Beispiel hierfür finden Sie unten.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

Um die Befehlsprozeduren weiter zu überprüfen, können Sie [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) und [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).
  
## <a name="configure-for-push-notifications"></a>Konfigurieren von Pushbenachrichtigungen
<a name="ConfigPush"> </a>

Push-Benachrichtigungen in Form von Abzeichen, Symbolen oder Warnungen können an ein mobiles Gerät gesendet werden, auch wenn die Skype-oder lync-App inaktiv ist. Was sind aber Push-Benachrichtigungen? Dabei handelt es sich um Ereignis Warnungen, wie eine neue oder verpasste sofortnachrichteneinladung oder für eine empfangene Voicemail. Der Skype for Business Server Mobilitätsdienst sendet diese Benachrichtigungen an den cloudbasierten Skype for Business Server Push-Benachrichtigungsdienst, der dann die Benachrichtigungen an den Microsoft Push Notification Service (MSNs) für Windows Phone Benutzer sendet.
  
Diese Funktionalität ist unverändert von lync Server 2013, aber wenn Sie über eine Skype for Business Server verfügen, sollten Sie die folgenden Schritte ausführen:
  
- Fügen Sie für eine Skype for Business Server Edgeserver einen neuen Hostinganbieter, Microsoft Skype for Business Online, hinzu, und richten Sie dann den Partnerverbund für den Hostinganbieter zwischen Ihrer Organisation und Skype for Business Online ein.
    
- Aktivieren Sie Push-Benachrichtigungen, indem Sie das Cmdlet " **CsPushNotificationConfiguration** " ausführen. Pushbenachrichtigungen sind standardmäßig deaktiviert.
    
- Testen Sie Ihre Verbund Konfiguration und Push-Benachrichtigungen.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Konfigurieren des Skype for Business Edgeserver für Push-Benachrichtigungen

1. Melden Sie sich mit einem Konto an, das Mitglied der **CsAdministrator** -Rolle ist, auf einem Computer, auf dem **Skype for Business Server Verwaltungsshell** und **OCSCore** installiert sind.
    
2. Starten Sie die **Skype for Business Server Management-Shell**.
    
3. Fügen Sie einen Skype for Business Server Online Hosting-Anbieter hinzu.
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Beispiel:
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > Sie können nicht mehr als eine partnerverbundbeziehung mit einem einzelnen Hostinganbieter haben. Wenn Sie also bereits einen Hostinganbieter eingerichtet haben, der eine partnerverbundbeziehung mit sipfed.online.lync.com hat, fügen Sie keinen weiteren Hostinganbieter hinzu, selbst wenn die Identität des hostinganbieters etwas anderes als SkypeOnline ist. 
  
4. Richten Sie den Partnerverbund für den Hostinganbieter zwischen Ihrer Organisation und dem Push-Benachrichtigungsdienst unter Skype for Business Online ein. An der Befehlszeile müssen Sie Folgendes eingeben:
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Aktivieren von Push-Benachrichtigungen

1. Melden Sie sich mit einem Konto an, das Mitglied der **CsAdministrator** -Rolle ist, auf einem Computer, auf dem **Skype for Business Server Verwaltungsshell** und **OCSCore** installiert sind.
    
2. Starten Sie die **Skype for Business Server Management-Shell**.
    
3. Aktivieren von Push-Benachrichtigungen:
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Partnerverbund aktivieren:
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>Testen von Verbund-und Push-Benachrichtigungen

1. Melden Sie sich mit einem Konto an, das Mitglied der **CsAdministrator** -Rolle ist, auf einem Computer, auf dem **Skype for Business Server Verwaltungsshell** und **OCSCore** installiert sind.
    
2. Starten Sie die **Skype for Business Server Management-Shell**.
    
3. Testen Sie die Verbund Konfiguration:
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    Beispiel:
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. Testen Sie Ihre Push-Benachrichtigungen:
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    Beispiel:
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>Konfigurieren der Mobilitätsrichtlinie
<a name="ConfigMob"> </a>

Sie haben die Möglichkeit, mit Skype for Business Server festzustellen, wer Ihren Mobilitätsdienst verwenden kann, wie Sie über Arbeit, VoIP (Voice over IP) oder Videoanrufen können, und ob WLAN für VoIP oder Video benötigt wird. Mit der Funktion "Anruf über Arbeit" kann ein mobiler Benutzer seine geschäftliche Telefonnummer anstelle seiner Mobiltelefonnummer beim Platzieren und empfangen von Anrufen verwenden. Die Person am anderen Ende der Leitung kann die Mobiltelefonnummer dieses mobilen Benutzers nicht sehen, sodass der Mobile Benutzer ausgehende Gesprächsgebühren vermeiden kann. Wenn VoIP und Video eingerichtet sind, können Benutzer VoIP-Anrufe und Videos durchführen und tätigen. Die Einstellungen für die WLAN-Nutzung bestimmen, ob das Mobile Gerät eines Benutzers ein WLAN-Netzwerk über ein Mobilfunknetz verwenden muss.
  
Mobilität, Anruf über Arbeit und VoIP-und Videofunktionen sind standardmäßig aktiviert. Die Einstellung WLAN für VoIP und Video erforderlich ist deaktiviert. Ein Administrator kann dies entweder global, nach Standort oder nach Benutzer ändern.
  
Um Mobilitätsfunktionen nutzen und über Arbeit anrufen zu können, müssen Benutzer folgende Aufgaben erfüllen:
  
- Für Skype for Business Server aktiviert
    
- Aktiviert für Enterprise-VoIP.
    
- Es wurde eine Mobilitätsrichtlinie zugewiesen, für die die Option **EnableMobility** auf **true**festgelegt ist.
    
Damit Benutzer die Funktion "Anruf über Arbeit" verwenden können, müssen Sie auch Folgendes sein:
  
- Es wurde eine VoIP-Richtlinie zugewiesen, für die die Option **Gleichzeitiges Klingeln von Telefonen aktivieren** aktiviert ist.
    
- Es wurde eine Mobilitätsrichtlinie zugewiesen, bei der die **Option enableoutsidevoice** auf **true**festgelegt ist.
    
> [!NOTE]
> Benutzer, die nicht für Enterprise-VoIP aktiviert sind, können mit ihren mobilen Geräten Skype-VoIP-Anrufe tätigen oder an Konferenzen teilnehmen, indem Sie auf Ihren mobilen Geräten die entsprechenden Optionen für die VoIP-Richtlinie festlegen, der Sie zugeordnet sind. mit. Im Planungsthema finden Sie weitere Details. 
  
### <a name="modify-global-mobility-policy"></a>Ändern der globalen Mobilitätsrichtlinie

1. Melden Sie sich mit einem Konto an, das Mitglied der **CsAdministrator** -Rolle ist, auf einem Computer, auf dem **Skype for Business Server Verwaltungsshell** und **OCSCore** installiert sind.
    
2. Starten Sie die **Skype for Business Server Management-Shell**.
    
3. Deaktivieren Sie den Zugriff auf Mobilität und rufen Sie über Work Global auf, indem Sie Folgendes eingeben:
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Sie können den Anruf über Arbeit deaktivieren, ohne den Zugriff auf Mobilität zu deaktivieren. Sie können die Mobilität jedoch nicht deaktivieren, ohne auch die Funktion "Anruf über Arbeit" zu deaktivieren. 
  
    Weitere Informationen finden Sie unter Festlegen von " [CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)".
    
### <a name="modify-mobility-policy-by-site"></a>Ändern der Mobilitätsrichtlinie nach Standort

1. Melden Sie sich mit einem Konto an, das Mitglied der **CsAdministrator** -Rolle ist, auf einem Computer, auf dem **Skype for Business Server Verwaltungsshell** und **OCSCore** installiert sind.
    
2. Starten Sie die **Skype for Business Server Management-Shell**.
    
3. Sie können eine Richtlinie auf Standortebene erstellen, VoIP und Video deaktivieren, WLAN für IP-Audio aktivieren und WLAN für IP-Video nach Standort benötigen. Typ:
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Weitere Informationen finden Sie unter [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-user"></a>Ändern der Mobilitätsrichtlinie nach Benutzer

1. Melden Sie sich mit einem Konto an, das Mitglied der **CsAdministrator** -Rolle ist, auf einem Computer, auf dem **Skype for Business Server Verwaltungsshell** und **OCSCore** installiert sind.
    
2. Starten Sie die **Skype for Business Server Management-Shell**.
    
3. Erstellen Sie mobilitätsrichtlinien auf Benutzerebene, und deaktivieren Sie die Mobilität und rufen Sie über Arbeit nach Benutzer auf. Typ:
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    Ein weiteres Beispiel mit Beispieldaten:
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > Sie können den Anruf über Arbeit deaktivieren, ohne den Zugriff auf Mobilität zu deaktivieren. Sie können die Mobilität jedoch nicht deaktivieren, ohne auch die Funktion "Anruf über Arbeit" zu deaktivieren. 
  

