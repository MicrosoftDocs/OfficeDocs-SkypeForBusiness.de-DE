---
title: Bereitstellen und Konfigurieren von Mobilität für Skype for Business Server
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
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: In diesem Artikel werden Die Schritte zum Konfigurieren einer vorhandenen Skype for Business Server-Installation für die Verwendung des Mobilitätsdiensts erläutert, sodass Ihre mobilen Geräte die Skype for Business Server Mobility-Funktionen nutzen können.
ms.openlocfilehash: 2ba0a81350dac6e47f4e909b4cfba256ee90de18
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103861"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Bereitstellen und Konfigurieren von Mobilität für Skype for Business Server  
 
In diesem Artikel werden Die Schritte zum Konfigurieren einer vorhandenen Skype for Business Server-Installation für die Verwendung des Mobilitätsdiensts erläutert, sodass Ihre mobilen Geräte die Skype for Business Server Mobility-Funktionen nutzen können.
  
Nachdem Sie den [Artikel Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) überprüft haben, sollten Sie mit den folgenden Schritten fortfahren, um Mobilität in Ihrer Skype for Business Server-Umgebung zu implementieren. Die Schritte sind wie folgt (und wir enthalten in dieser Tabelle eine Berechtigungsliste):
  
|**Phase**|**Berechtigungen**|
|:-----|:-----|
|[Erstellen von DNS-Einträgen](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Domänen-Admins  <br/> DNSAdmins  <br/> |
|[Ändern von Zertifikaten](deploy-and-configure-mobility.md#ModCerts) <br/> |Lokaler Administrator  <br/> |
|[Konfigurieren des Reverseproxys](deploy-and-configure-mobility.md#ConfigRP) <br/> |Lokaler Administrator  <br/> |
|[Konfigurieren der AutoErmittlung für Mobilität mit Hybridbereitstellungen](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domänen-Admins  <br/> |
|[Testen Der Mobilitätsbereitstellung](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[Konfigurieren von Pushbenachrichtigungen](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[Konfigurieren der Mobilitätsrichtlinie](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
Alle folgenden Abschnitte enthalten Schritte, die davon ausgehen, dass Sie das Thema Planning gelesen haben. Wenn Sie etwas verwirrend sind, können Sie sich die Informationen dort auschecken.

> [!NOTE]
> McX(Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen mobilen Skype for Business-Clients verwenden bereits die Unified Communications Web API (UCWA) zur Unterstützung von Chat, Anwesenheit und Kontakten. Benutzer mit Legacyclients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
## <a name="create-dns-records"></a>Erstellen von DNS-Einträgen
<a name="CreateDNSRec"> </a>

Sie haben diese möglicherweise bereits als Teil Ihrer Skype for Business Server-Umgebung, sie müssen jedoch die folgenden Datensätze erstellen, damit die AutoErmittlung funktioniert:
  
- Ein interner DNS-Eintrag zur Unterstützung mobiler Benutzer, die über das Netzwerk Ihrer Organisation eine Verbindung herstellen.
    
- Ein externer (oder öffentlicher) DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung von außerhalb des Unternehmensnetzwerks herstellen.
    
Diese Datensätze können entweder A(Host)-Namen oder #A0 sein (Sie müssen nicht beides machen, wir enthalten hier nur die Schritte für alles).
  
### <a name="create-an-internal-dns-cname-record"></a>Erstellen eines internen DNS-CNAME-Eintrags

1. Melden Sie sich bei einem DNS-Server in Ihrem Netzwerk an, der entweder Mitglied der Gruppe **"Domänen-Admins"** oder **"DnsAdmins"** ist.
    
2. Klicken **Sie auf Start,** Administrative  **Tools** auswählen (sie müssen möglicherweise suchen, wenn es keine Option im Startmenü ist), und klicken Sie dann auf **DNS,** um das administrative DNS-Snap-In zu öffnen.
    
3. Im linken Bereich des Konsolenfensters müssen Sie zu der Domäne wechseln, in der sich die Front-End-Server  Ihres Skype for Business Servers befinden, und die Weiterleitungs-Nachschlagezonen dort erweitern.
    
4. Nehmen Sie sich einen Moment Zeit, um zu sehen, welche der folgenden Optionen Sie haben:
    
   - Alle Host-A- oder AAAA-Einträge für Ihren Front-End-Server (Standard oder Enterprise) oder Front-End-Pool(n).
    
   - Alle Host-A- oder AAAA-Einträge für einen Director- oder Directorpool (eine optionale Konfiguration, die Sie möglicherweise in Ihrer Bereitstellung haben).
    
5. Nachdem Sie dies bemerkt haben, klicken Sie mit der rechten Maustaste auf Ihren #A0 und wählen Dann im Menü **neuen Alias (CNAME)** aus.
    
6. Geben Sie **im Textfeld Aliasname** lyncdiscoverinternal für Den Hostnamen für die interne AutoErmittlungsdienst-URL ein.
    
7. Im **Vollqualifizierten Domänennamen (FQDN** für Zielhost) müssen Sie den internen FQDN der Webdienste für Ihren Front-End-Pool (oder einen einzelnen Front-End-Server oder Directorpool oder Director) eingeben oder zu diesem navigieren, der in Schritt 4 oben angegeben ist. Klicken Sie auf OK, wenn sie eingegeben wird.
    
8. Sie müssen einen neuen AutoErmittlungs-CNAME-Eintrag in der Nachschlagezone für jede #A0 erstellen, die in Ihrer Skype for Business #A1 unterstützt wird.
    
### <a name="create-an-external-dns-cname-record"></a>Erstellen eines externen DNS-CNAME-Eintrags

1. Diese Schritte sind generisch, da wir nicht wissen können, welchen öffentlichen DNS-Anbieter Sie möglicherweise verwenden, aber wir möchten Ihnen weiterhin helfen. Melden Sie sich bei Ihrem öffentlichen DNS-Anbieter mit einem Konto an, das dort neue DNS-Einträge erstellen kann.
    
2. Zu diesem Zeitpunkt sollte dort bereits eine SIP-Domäne für Skype for Business Server vorhanden sein. Erweitern Sie **die Forward Lookup Zone** für diese SIP-Domäne, oder öffnen Sie sie anderweitig.
    
3. Nehmen Sie sich einen Moment Zeit, um zu sehen, welche der folgenden Optionen Sie haben:
    
   - Alle Host-A- oder AAAA-Einträge für Ihren Front-End-Server (Standard oder Enterprise) oder Front-End-Pool(n).
    
   - Alle Host-A- oder AAAA-Einträge für einen Director- oder Directorpool (eine optionale Konfiguration, die Sie möglicherweise in Ihrer Bereitstellung haben).
    
4. Sobald Sie über diese Informationen verfügen, sollten Sie in der Lage sein, eine Option zum Erstellen eines neuen **Alias (CNAME) auszuwählen.**
    
5. Jetzt sollten Sie einen **Aliasnamen** eingeben können, sie müssen hier lyncdiscover für die externe AutoErmittlungsdienst-URL eingeben.
    
6. Als Nächstes sollte ein Bereich in einen **FQDN** für den Zielhost eingeben werden. Dies muss der FQDN für Ihren Front-End-Pool (oder einzelner Front-End-Server oder Directorpool oder Director), der in Schritt 3 oben angegeben ist.
    
7. Möglicherweise müssen Sie hier speichern, oder wenn Sie zusätzliche #A0 in der Nachschlagezone jeder #A1 in Ihrer Skype for Business #A1 erstellen müssen, sollten Sie dies tun, aber sobald Sie bereit sind, speichern Sie Ihre Arbeit.
    
### <a name="create-an-internal-dns-a-record"></a>Erstellen eines internen DNS A-Eintrags

1. Melden Sie sich bei einem DNS-Server in Ihrem Netzwerk an, der entweder Mitglied der Gruppe **"Domänen-Admins"** oder **"DnsAdmins"** ist.
    
2. Klicken **Sie auf Start,** Administrative  **Tools** auswählen (sie müssen möglicherweise suchen, wenn es keine Option im Startmenü ist), und klicken Sie dann auf **DNS,** um das administrative DNS-Snap-In zu öffnen.
    
3. Im linken Bereich des Konsolenfensters müssen Sie zu der Domäne wechseln, in der sich die Front-End-Server  Ihres Skype for Business Servers befinden, und die Weiterleitungs-Nachschlagezonen dort erweitern.
    
4. Nehmen Sie sich einen Moment Zeit, um zu sehen, welche der folgenden Optionen Sie haben:
    
   - Alle Host-A- oder AAAA-Einträge für Ihren Front-End-Server (Standard oder Enterprise) oder Front-End-Pool(n).
    
   - Alle Host-A- oder AAAA-Einträge für einen Director- oder Directorpool (eine optionale Konfiguration, die Sie möglicherweise in Ihrer Bereitstellung haben).
    
5. Nachdem Sie dies bemerkt haben, klicken Sie mit der rechten Maustaste auf Ihren SIP-Domänennamen, und wählen Sie dann im Menü Neuen Host (A oder **AAAA)** aus.
    
6. Geben Sie **im Textfeld Name** lyncdiscoverinternal für Den Hostnamen für die interne AutoErmittlungsdienst-URL ein.
    
7. Geben Sie **im Textfeld IP-Adresse** die interne Webdienst-IP-Adresse für Ihren Front-End-Pool (oder einen einzelnen Front-End-Server oder Directorpool oder Director) ein, die in Schritt 4 oben angegeben ist.
    
8. Klicken Sie dann auf **Host hinzufügen,** und klicken Sie dann auf **OK**.
    
9. Sie müssen neue AutoErmittlungS- oder AAAA-Einträge in der Nachschlagezone für jede in Ihrer Skype for Business Server-Umgebung unterstützte SIP-Domäne erstellen. Wiederholen Sie dazu die Schritte 6 bis 8 so oft wie erforderlich.
    
10. Wenn Sie fertig sind, klicken Sie auf **Fertig**.
    
### <a name="create-an-external-dns-a-record"></a>Erstellen eines externen DNS A-Eintrags

1. Diese Schritte sind generisch, da wir nicht wissen können, welchen öffentlichen DNS-Anbieter Sie möglicherweise verwenden, aber wir möchten Ihnen weiterhin helfen. Melden Sie sich bei Ihrem öffentlichen DNS-Anbieter mit einem Konto an, das dort neue DNS-Einträge erstellen kann.
    
2. Zu diesem Zeitpunkt sollte dort bereits eine SIP-Domäne für Skype for Business Server vorhanden sein. Erweitern Sie **die Forward Lookup Zone** für diese SIP-Domäne, oder öffnen Sie sie anderweitig.
    
3. Nehmen Sie sich einen Moment Zeit, um zu sehen, welche der folgenden Optionen Sie haben:
    
   - Alle Host-A- oder AAAA-Einträge für Ihren Front-End-Server (Standard oder Enterprise) oder Front-End-Pool(n).
    
   - Alle Host-A- oder AAAA-Einträge für einen Director- oder Directorpool (eine optionale Konfiguration, die Sie möglicherweise in Ihrer Bereitstellung haben).
    
4. Sobald Sie über diese Informationen verfügen, sollten Sie in der Lage sein, eine Option zum Erstellen eines neuen **Hosts A oder AAAA auszuwählen.**
    
5. Jetzt sollten Sie einen Namen eingeben **können,** sie müssen hier lyncdiscover für die externe AutoErmittlungsdienst-URL eingeben.
    
6. Als Nächstes sollte ein Bereich vorhanden sein, der in eine IP-Adresse eingeben soll. **Dies** muss die IP für Ihren Front-End-Pool (oder einzelner Front-End-Server oder Directorpool oder Director) sein, der in Schritt 3 oben angegeben ist.
    
7. Möglicherweise müssen Sie hier speichern, oder wenn Sie zusätzliche A- oder AAAA-Einträge in der Nachschlagezone jeder SIP-Domäne für Ihre Skype for Business Server-Umgebung erstellen müssen, sollten Sie dies tun, aber sobald Sie bereit sind, speichern Sie Ihre Arbeit.
    
## <a name="modify-certificates"></a>Ändern von Zertifikaten
<a name="ModCerts"> </a>

Wenn Sie Fragen zum Planen von Zertifikaten haben, haben wir dies in unserem [Artikel Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) dokumentiert. Nachdem Sie dies überprüft haben, werden wir Sie durch die folgenden Schritte gehen:
  
- Brauche ich neue Zertifikate?
    
- Anfordern neuer Zertifikate von Ihrer Zertifizierungsstelle
    
- Aktualisieren Ihrer vorhandenen Zertifikate mit den Ersetzungen mithilfe von PowerShell.
    
- Überprüfen der Zertifikate mithilfe des Zertifikat-Snap-Ins in der Microsoft Management Console (MMC).
    
### <a name="do-i-need-new-certificates"></a>Brauche ich neue Zertifikate?

1. Zunächst müssen Sie möglicherweise überprüfen und sehen, welche Zertifikate verfügbar sind und ob sie über die benötigten Einträge verfügen. Dazu müssen Sie sich bei Ihrem Skype for Business Server mit einem Konto anmelden, das ein lokaler Administrator ist. Dieses Konto muss möglicherweise auch über Rechte an der ausstellenden Zertifizierungsstelle (Certificate Authority, CA) für einige dieser Schritte verfügen.
    
2. Öffnen Sie die Skype for Business Server-Verwaltungsshell (Sie können die Suche verwenden, um sie zu finden, wenn sie nicht an Das Startmenü oder die Taskleiste angeheftet ist).
    
3. Es ist wichtig, dass Sie wissen, welche Zertifikate zugewiesen wurden, bevor Sie versuchen, ein aktualisiertes Zertifikat zu hinzufügen. Geben Sie also beim Befehl folgenden Befehl ein:
    
   ```powershell
   Get-CsCertificate
   ```

4. Die Informationen aus Schritt 3 sind für Sie eindeutig. Sie müssen nachschauen, um festzustellen, ob Ihnen ein einzelnes Zertifikat zugewiesen wurde, das für mehrere Dinge zugewiesen wurde, oder ob Ihnen ein anderes Zertifikat für die verschiedenen Komponenten zugewiesen ist, die sie benötigen. Mit **dem Parameter Use** erfahren Sie, wie ein Zertifikat verwendet wird, und der Parameter **Thumbprint** gibt Ihnen an, ob es sich um dasselbe Zertifikat oder mehrere Certs gibt.
    
5. Wenn Sie die san-Einträge im Abschnitt Planung empfohlen haben, sind Sie gut. Andern falls nicht, müssen Sie ein neues Zertifikat oder mehrere Zertifikate (je nach Konfiguration) von Ihrer Zertifizierungsstelle anfordern.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>Anfordern eines neuen Zertifikats oder Zertifikats von Ihrer Zertifizierungsstelle

1. Nachdem Sie überprüft haben, welche SAN-Einträge Sie haben, wissen Sie, dass Sie über ein einzelnes Zertifikat **verfügen** (nachdem Sie die obigen Schritte überprüft haben), und Sie haben erfahren, dass Sie nicht über alle benötigten Einträge verfügen. Eine neue Zertifikatanforderung muss an Ihre Zertifizierungsstelle gestellt werden. Öffnen Sie Ihre Skype for Business Server PowerShell:
    
   - Für ein fehlendes AutoErmittlungsdienst-SAN (Ersetzen des Parameters -Ca durch Einen eigenen Pfad der Zertifizierungsstelle):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Wenn Sie nun über mehrere SIP-Domänen verfügen, können Sie den AllSipDomain-Parameter nicht wie im obigen Beispiel verwenden. Sie müssen stattdessen den Parameter DomainName verwenden. Und wenn Sie den Parameter DomainName verwenden, müssen Sie den FQDN für die lyncdiscoverinternal- und lyncdiscover-Datensätze definieren. Ein Beispiel wäre (ersetzen Sie den -Ca-Parameter durch Ihren eigenen Pfad für die Zertifizierungsstelle):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. Nachdem Sie überprüft haben, welche SAN-Einträge Sie haben,  haben Sie auch mehrere Zertifikate gefunden, die nicht über alle benötigten Einträge verfügen. Eine neue Zertifikatanforderung muss an Ihre Zertifizierungsstelle gestellt werden. Öffnen Sie Ihre Skype for Business Server PowerShell:
    
   - Für ein fehlendes AutoErmittlungsdienst-SAN (Ersetzen des Parameters -Ca durch Einen eigenen Pfad der Zertifizierungsstelle):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Wenn Sie nun über mehrere SIP-Domänen verfügen, können Sie den AllSipDomain-Parameter nicht wie im obigen Beispiel verwenden. Sie müssen stattdessen den Parameter DomainName verwenden. Und wenn Sie den Parameter DomainName verwenden, müssen Sie den FQDN für die lyncdiscoverinternal- und lyncdiscover-Datensätze definieren. Beispiele wären (Ersetzen des Parameters -Ca durch Einen eigenen Pfad der Zertifizierungsstelle):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - Nachdem die neuen Zertifikate von der Zertifizierungsstelle generiert wurden, müssen Sie sie zuweisen.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Zuweisen von Zertifikaten mithilfe der Skype for Business Server-Verwaltungsshell

- Je nachdem, was Sie oben im Abschnitt Benötigen Sie neue Zertifizierungen gefunden haben, müssen Sie eine **der** folgenden Schritte ausführen.
    
  - Wenn Sie über ein einzelnes Zertifikat für alles verfügen (die Fingerabdrucke sind identisch), müssen Sie dies ausführen:
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - Wenn Sie unterschiedliche Zertifikate für Dinge haben (die Fingerabdrucks sind alle unterschiedlich), führen Sie stattdessen dies aus:
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Anzeigen von Zertifikaten in der Microsoft Management Console (MMC)

1. Sie haben die Möglichkeit, ihre Zertifikate mithilfe des Zertifikat-Snap-Ins für das MMC zu betrachten. Geben Sie mmC einfach in die Suche ein, und es sollte als Anwendungsoption angezeigt werden.
    
2. Zum Hinzufügen des Zertifikat-Snap-Ins müssen Sie auf **Datei** klicken und dann **Snap-In hinzufügen/entfernen...** (oder die Tastenkombination **STRG+M** funktioniert ebenfalls). **Zertifikate** sind eine Option im linken Bereich, wählen  Sie sie aus, und klicken Sie dann im Popupfenster auf Computerkonto und dann **auf Weiter**.
    
3. Bleiben Sie weiterhin im Popupfenster, mit aller Wahrscheinlichkeit tun Sie dies auf dem Computer, auf dem  die Zertifikate gespeichert sind, die Sie sich anzeigen müssen. Lassen Sie die Auswahl daher auf dem lokalen Computer, wenn dies so ist. Wenn Sie auf einem Remotecomputer arbeiten, ändern Sie das Optionsfeld in einen anderen **Computer,** und  geben Sie dann entweder den FQDN dieses Computers ein, oder verwenden Sie die Schaltfläche Durchsuchen, um über AD nach diesem Computer zu suchen. Nachdem Sie den Computer ausgewählt haben, müssen Sie auf Fertig stellen klicken, wenn sie bereit sind, und dann **OK,** um das Snap-In zum MMC hinzuzufügen. 
    
4. Erweitern Sie **den Abschnitt** Zertifikate im linken Bereich des MMC. Erweitern Sie **auch** den Ordner Personal, und wählen Sie dann **Zertifikate aus.** Dadurch können Sie die Zertifikate in diesem Speicher sehen.
    
5. Sie müssen das Zertifikat suchen, das Sie anzeigen möchten, klicken Sie mit der rechten Maustaste darauf, und wählen Sie **Öffnen aus.**
    
    > [!NOTE]
    > Wo wissen Sie, um welches Zertifikat es sich handelt? Es sollte entweder das einzelne Zertifikat sein, das für ihre Farm zugewiesen ist, oder Sie verfügen möglicherweise über mehrere Zertifikate für verschiedene Dinge, z. B. Standard, interne Webdienste usw., in diesem Fall müssen Sie sich möglicherweise mehrere Zertifikate anschauen. Mehrere Zertifikate haben denselben Fingerabdruck. 
  
6. Nachdem Sie die Zertifikatansicht  erhalten haben, wählen Sie **Details aus.** Dadurch wird der Name des Zertifikatssubjekts angezeigt, wenn Sie **Betreff** auswählen, und der zugewiesene Betreffname und die zugehörigen Eigenschaften werden angezeigt.
    
7. Sie müssen auch die Einträge **"Alternativer Betreffname"** überprüfen. Sie finden eine oder mehrere der folgenden Optionen:
    
   - Der Poolname für diesen Pool oder der Name eines einzelnen Servers, wenn es sich nicht um einen Pool handelt.
    
   - Der Servername, dem das Zertifikat zugewiesen ist.
    
   - Einfache URL-Datensätze, in der Regel meet und dialin.
    
   - Interne und externe Web Services-Namen von Webdiensten (z. B. webpool01.contoso.net, webpool01.contoso.com), basierend auf den Im Topologie-Generator getroffenen Optionen und der Auswahl überlasteter Webdienste.
    
   - Wenn bereits zugewiesen, die lyncdiscover.\<sipdomain\> und lyncdiscoverinternal.\<sipdomain\> Datensätze.
    
     Sie müssen mehrere Zertifikate überprüfen, wenn Mehr als ein Zertifikat zugewiesen ist (überprüfen Sie den obigen Hinweis).
    
8. Wenn Sie also lyncdiscover finden.\<sipdomain\> und lyncdiscoverinternal.\<sipdomain\> datensätze, sie haben dies bereits konfiguriert. Sie können den MMC schließen.
    
9. Wenn sie nicht zugewiesen sind, müssen Sie entweder eine neue Zertifikatanforderung stellen (oben beschrieben) oder sie nach der Anforderung installieren (dazu empfehlen wir Die oben aufgeführte PowerShell).
    
## <a name="configure-the-reverse-proxy"></a>Konfigurieren des Reverseproxys
<a name="ConfigRP"> </a>

Die folgenden Schritte sind nicht dazu gedacht, genau befolgt zu werden. Das liegt daran, dass wir Sie in früheren Versionen des Produkts durchgegangen wären, z. B. das Konfigurieren von Threat Management Gateway (TMG), und wenn Sie dies nicht verwendet haben, müssten Sie von dort aus Eine eigene Version ausarbeiten.
  
TMG wird von Microsoft nicht mehr als Produkt angeboten, und wenn Sie es noch konfigurieren müssen, können Sie sich die [Lync Server 2013-Schritte anschauen.](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-the-reverse-proxy-for-mobility) Die folgenden Informationen sollen jedoch generell hilfreich sein, auch wenn es keine Möglichkeit gibt, bestimmte exemplarische Vorgehensweisen für jeden Reverseproxy zu bieten.
  
Es gibt zwei wichtige Punkte, die wir berücksichtigen müssen:
  
- Werden Sie Ihre anfängliche AutoErmittlungsanforderung über HTTPS (was wir empfehlen) tun?
    
  - Wenn Sie über eine Webveröffentlichungsregel verfügen, müssen Sie sie ändern.
    
  - Wenn Sie noch keine Webveröffentlichungsregel haben, müssen Sie sie erstellen.
    
- Wenn Sie Ihre anfängliche AutoErmittlungsanforderung über HTTP erstellen, müssen Sie auch diese Regel erstellen oder ändern.
    
> [!NOTE]
> **Wichtig** Ein Proxy-Time-Out-Wert ist eine Zahl, die von Bereitstellung zu Bereitstellung unterschiedlich ist. Sie sollten Ihre Bereitstellung überwachen und den Wert für die beste Benutzererfahrung für Clients ändern. Möglicherweise können Sie den Wert auf 200 festlegen. Wenn Sie mobile Lync-Clients in Ihrer Umgebung unterstützen, sollten Sie den Wert auf 960 festlegen, um Pushbenachrichtigungs-Time-Outs von Office 365 zu ermöglichen, die einen Zeitsendwert von 900 haben. Es ist sehr wahrscheinlich, dass Sie den Zeitpunktwert erhöhen müssen, um Clienttrennungen zu vermeiden, wenn der Wert zu niedrig ist, oder die Anzahl zu verringern, wenn Verbindungen über den Proxy nicht getrennt werden, aber lange nach der Verbindung mit dem Client getrennt werden. Überwachung und Baslerining, was für Ihre Umgebung üblich ist, ist die einzige genaue Möglichkeit, die entsprechende Einstellung für diesen Wert zu ermitteln.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Ändern der vorhandenen Webveröffentlichungsregel für Ihr externes AutoErmittlungs-SAN und ihre URL

1. Öffnen Sie die Reverseproxyschnittstelle.
    
2. Sie müssen Ihre Webveröffentlichungsregel suchen und die Option Bearbeiten auswählen (je nach Reverseproxykonfiguration kann sie sich auf einem Menü oder einer Registerkarte befindet).
    
3. Es sollte einen Bereich mit der Anwendung dieser Webveröffentlichungsregel gibt. Sie müssen diese Regel für eingehende Websites oder Anforderungen für Websites ändern. Sie fügen einen **neuen** Eintrag hinzu.
    
4. Geben Sie den Namen Ihrer AutoErmittlungswebsite ein (das Beispiel, das wir verwenden, ist lyncdiscover.contoso.com), und klicken Sie abhängig vom Format Ihres Reverseproxys auf **OK** oder Speichern.
    
5. Möglicherweise verfügen Sie über ein neues Zertifikat mit dem AutoErmittlungs-SAN-Eintrag. Dies muss ebenfalls installiert und entsprechend den Einstellungen Ihres Reverseproxys für die Verwendung konfiguriert werden. Achten Sie darauf, alles zu speichern, wenn die Konfiguration abgeschlossen ist.
    
6. Wenn Ihr Reverseproxy über eine **Testfunktionalität** verfügt, verwenden Sie diese, um sicherzustellen, dass alles ordnungsgemäß funktioniert.
    
7. Möglicherweise müssen Sie diese Schritte jetzt wiederholen, wenn Sie über einen Director- oder Directorpool in Ihrer Umgebung verfügen (dies würde bedeuten, dass Sie über eine zweite Regel verfügen).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Erstellen einer Webveröffentlichungsregel für die externe AutoErmittlungs-URL

1. Öffnen Sie die Reverseproxyschnittstelle.
    
2. Sie müssen auf der Benutzeroberfläche suchen, wo Sie Ihre Webveröffentlichungsregeln erstellen, und die Option **Neu** oder Erstellen auswählen (je nach Reverseproxykonfiguration kann sie sich auf einem Menü oder einer Registerkarte befindet).  Sie suchen nach der Option zum Erstellen einer neuen Webveröffentlichungsregel.
    
3. In der Regel müssen Sie die folgenden Informationen eingeben:
    
   - **Name**: der Name ihrer Regel
    
   - **Regelaktion**: In diesem Fall ist es eine **Allow-Regel,** sie lässt etwas über Ihren Reverseproxy passieren.
    
   - Die **Veröffentlichungsregel** oder Option, die Sie auswählen, wäre eine einzelne **Website oder ein Lastenausgleich.**
    
   - Dies muss **SSL für** den externen Zugriff sein, wählen Sie diese Option aus.
    
   - Sie müssen einen Pfad für die interne Veröffentlichung veröffentlichen und den FQDN für die externen Webdienste im Lastenausgleich des Front-End-Pools eingeben (oder den FQDN des Lastenausgleichspools, wenn Sie einen haben), ein Beispiel wäre sfb_pool01.contoso.local.
    
   - Sie sollten _ als pfad eingeben, der veröffentlicht werden soll, Sie müssen jedoch **/\\** auch den ursprünglichen Hostheader**weiterleiten.
    
   - Es gibt eine Option für **öffentliche oder externe Namensdetails** oder -informationen. Dies ist der Ort, an dem Sie eingeben können:
    
   - **Akzeptieren Sie Anforderungen,** aber es sollte für den Domänennamen sein.
    
   - Geben Sie **für den Namen** **lyncdiscover ein.** <sipdomain> (Dies ist die externe AutoErmittlungsdienst-URL). Wenn Sie nun eine Regel für die externe Webdienst-URL im Front-End-Pool erstellen, müssen Sie den FQDN für die externen Webdienste im Front-End-Pool eingeben (z. B. lyncwebextpool01.contoso.com).
    
   - Es gibt eine **Path-Option,** und Sie müssen **/\\** hier * eingeben.
    
   - Sie müssen einen **SSL-Listener** mit Ihrem aktuellen öffentlichen Zertifikat auswählen.
    
   - **Die Authentifizierungsdelegierung** sollte auf **Keine Delegierung** festgelegt sein, aber die direkte **Clientauthentifizierung** sollte zulässig sein.
    
   - Die Regel sollte auf Alle **Benutzer festgelegt werden.**
    
   - Dies sollten alle Informationen sein, die Sie zum Erstellen dieser Regel benötigen, damit Sie fortfahren können.
    
4. Sie müssen sicherstellen, dass der ursprüngliche **Hostheader** weitergeleitet wird.
    
5. Die **Webserverports** müssen ebenfalls festgelegt werden. Gehen Sie wie folgt vor:
    
   - **Umleitungsanforderungen an den HTTP-Port,** und die Portnummer sollte **8080 sein.**
    
   - **Umleitungsanforderungen an den SSL-Port,** und die Portnummer sollte **4443 sein.**
    
6. Wenn alles konfiguriert ist, müssen Sie diese speichern oder anwenden und dann die Regel testen.
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>Erstellen einer Webveröffentlichungsregel für Port 80 (Optional)

1. Öffnen Sie die Reverseproxyschnittstelle.
    
2. Sie müssen auf der Benutzeroberfläche suchen, wo Sie Ihre Webveröffentlichungsregeln erstellen, und die Option **Neu** oder Erstellen auswählen (je nach Reverseproxykonfiguration kann sie sich auf einem Menü oder einer Registerkarte befindet).  Sie suchen nach der Option zum Erstellen einer neuen Webveröffentlichungsregel.
    
3. In der Regel müssen Sie die folgenden Informationen eingeben:
    
   - **Name**: der Name ihrer Regel
    
   - **Regelaktion**: In diesem Fall ist es eine **Allow-Regel,** sie lässt etwas über Ihren Reverseproxy passieren.
    
   - Die **Veröffentlichungsregel** oder Option, die Sie auswählen, wäre eine einzelne **Website oder ein Lastenausgleich.**
    
   - Dies muss eine nicht gesicherte Verbindung sein, um eine Verbindung mit **dem veröffentlichten Webserver oder der veröffentlichten Farm herzustellen.**
    
   - Sie müssen einen Pfad für die interne Veröffentlichung veröffentlichen und den FQDN für die **VIP-Adresse** des Lastenausgleichs des Front-End-Pools eingeben, ein Beispiel wäre sfb_pool01.contoso.local.
    
   - Sie sollten _ als pfad eingeben, der veröffentlicht werden soll, Sie müssen jedoch **/\\** auch den ursprünglichen Hostheader**weiterleiten.
    
   - Es gibt eine Option für **öffentliche oder externe Namensdetails** oder -informationen. Dies ist der Ort, an dem Sie eingeben können:
    
   - **Akzeptieren Sie Anforderungen,** aber es sollte für den Domänennamen sein.
    
   - Geben Sie **für den Namen** **lyncdiscover ein.** <sipdomain> (Dies ist die externe AutoErmittlungsdienst-URL).
    
   - Es gibt eine **Path-Option,** und Sie müssen **/\\** hier * eingeben.
    
   - Sie müssen einen Weblistener auswählen oder Ihrem Reverseproxy erlauben, einen für Sie zu erstellen.
    
   - **Die Authentifizierungsdelegierung** sollte auf **Keine Delegierung** festgelegt sein, aber die direkte **Clientauthentifizierung sollte nicht** zulässig sein.
    
   - Die Regel sollte auf Alle **Benutzer festgelegt werden.**
    
   - Dies sollten alle Informationen sein, die Sie zum Erstellen dieser Regel benötigen, damit Sie fortfahren können.
    
4. Die **Webserverports** müssen festgelegt werden. Gehen Sie wie folgt vor:
    
   - **Umleitungsanforderungen an den HTTP-Port,** und die Portnummer sollte **8080 sein.**
    
   - **Umleitungsanforderungen an den SSL-Port,** und die Portnummer sollte **4443 sein.**
    
5. Wenn alles konfiguriert ist, müssen Sie diese speichern oder anwenden und dann die Regel testen.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Konfigurieren der AutoErmittlung für Mobilität mit Hybridbereitstellungen
<a name="ConfigAutoD"> </a>

Hybridumgebungen in Skype for Business Server sind Umgebungen, die eine lokale und eine O365-Umgebung kombinieren. Wenn Skype for Business Server in einer Hybridumgebung arbeitet, muss der AutoErmittlungsdienst in der Lage sein, einen Benutzer aus einer dieser Umgebungen zu finden.
  
Damit mobile Clients ermitteln können, wo sich ein Benutzer befindet, muss der AutoErmittlungsdienst mit einem neuen einheitlichen Ressourcen-Locator (URL) konfiguriert werden. Das sind die Schritte:
  
1. Öffnen Sie die Skype for Business Server-Verwaltungsshell.
    
2. Führen Sie folgendes aus, um den Wert des Attributs **ProxyFQDN** für Ihre Skype for Business Server-Umgebung zu erhalten:
    
   ```powershell
   Get-CsHostingProvider
   ```

3. Führen Sie dann weiterhin im Shellfenster aus:
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    Dabei wird [identity] durch den Domänennamen des freigegebenen SIP-Adressraums ersetzt.
    
## <a name="test-your-mobility-deployment"></a>Testen Der Mobilitätsbereitstellung
<a name="TestMobility"> </a>

Nachdem Sie den Skype for Business Server Mobility Service und den Skype for Business Server AutoErmittlungsdienst bereitgestellt haben, sollten Sie eine Testtransaktion ausführen, um sicherzustellen, dass Ihre Bereitstellung richtig funktioniert. Sie können **Test-CsUcwaConference** ausführen, um die Fähigkeit von zwei Benutzern zum Erstellen, Beitreten und Kommunizieren in einer Konferenz zu testen. Sie benötigen zwei Benutzer (real oder test) und ihre vollständigen Anmeldeinformationen, um diese Tests durchführen zu können. Dieser Befehl funktioniert sowohl für Skype for Business-Clients als auch für Lync Server 2013-Clients.
  
Für Lync Server 2010-Clients auf Skype for Business Server 2015 müssen Sie **Test-CsMcxP2PIM** zum Testen ausführen. Ihre Lync Server 2010-Benutzer müssen weiterhin tatsächliche Benutzer oder vordefinierte Testbenutzer sein, und Sie benötigen ihre Kennwortanmeldeinformationen.

> [!NOTE]
> McX(Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen mobilen Skype for Business-Clients verwenden bereits die Unified Communications Web API (UCWA) zur Unterstützung von Chat, Anwesenheit und Kontakten. Benutzer mit Legacyclients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Testen von Konferenzen für mobile Skype for Business- und Lync 2013-Clients

1. Melden Sie sich als Mitglied der **Rolle "CsAdministrator"** auf jedem Computer an, auf dem **Skype for Business Server Management Shell** und **Ocscore** installiert sind.
    
2. Starten Sie **die Skype for Business Server Management Shell** (Sie können den Namen in der Suche eingeben oder zu Alle **Programme** wechseln und ihn auswählen).
    
3. Geben Sie an der Befehlszeile ein:
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   Außerdem können Anmeldeinformationen in einem Skript festgelegt und an das Test-Cmdlet übergeben werden. Nachfolgend finden Sie ein Beispiel dafür.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Testen von Konferenzen für mobile Lync 2010-Clients

> [!NOTE]
> McX(Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen mobilen Skype for Business-Clients verwenden bereits die Unified Communications Web API (UCWA) zur Unterstützung von Chat, Anwesenheit und Kontakten. Benutzer mit Legacyclients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.

1. Melden Sie sich als Mitglied der **Rolle "CsAdministrator"** auf jedem Computer an, auf dem **Skype for Business Server Management Shell** und **Ocscore** installiert sind.
    
2. Starten Sie **die Skype for Business Server Management Shell** (Sie können den Namen in der Suche eingeben oder zu Alle **Programme** wechseln und ihn auswählen).
    
3. Geben Sie an der Befehlszeile ein:
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   Außerdem können Anmeldeinformationen in einem Skript festgelegt und an das Test-Cmdlet übergeben werden. Nachfolgend finden Sie ein Beispiel dafür.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

Weitere Informationen zu den Befehlsprozeduren finden Sie unter [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) und [Test-CsMcxP2PIM](/powershell/module/skype/test-csmcxp2pim?view=skype-ps).
  
## <a name="configure-for-push-notifications"></a>Konfigurieren von Pushbenachrichtigungen
<a name="ConfigPush"> </a>

Pushbenachrichtigungen in Form von Signalen, Symbolen oder Warnungen können an ein mobiles Gerät gesendet werden, auch wenn die Skype- oder Lync-App inaktiv ist. Doch was sind Pushbenachrichtigungen? Dabei handelt es sich um Ereigniswarnungen, z. B. eine neue oder verpasste Sofortnachrichteneinladung oder für eine empfangene Voicemail. Der Skype for Business Server Mobility-Dienst sendet diese Benachrichtigungen an den cloudbasierten Skype for Business Server-Pushbenachrichtigungsdienst, der dann die Benachrichtigungen an den Microsoft Push Notification Service (MSNS) für Windows Phone sendet.
  
Diese Funktionalität ist gegenüber Lync Server 2013 unverändert, aber wenn Sie über einen Skype for Business Server verfügen, müssen Sie die folgenden Schritte tun:
  
- Fügen Sie für einen Skype for Business Server Edge Server einen neuen Hostinganbieter hinzu, Microsoft Skype for Business Online, und richten Sie dann einen Hostinganbieterverbund zwischen Ihrer Organisation und Skype for Business Online ein.
    
- Aktivieren Sie Pushbenachrichtigungen, indem Sie das **Cmdlet Set-CsPushNotificationConfiguration** ausführen. Pushbenachrichtigungen sind standardmäßig deaktiviert.
    
- Testen Sie die Verbundkonfiguration und Pushbenachrichtigungen.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Konfigurieren Ihres Skype for Business Edge Servers für Pushbenachrichtigungen

1. Melden Sie sich mit einem Konto an, das Mitglied der **Rolle "CsAdministrator"** ist, auf einem Computer, auf dem **Skype for Business Server Management Shell** und **Ocscore** installiert sind.
    
2. Starten Sie **die Skype for Business Server Management Shell**.
    
3. Fügen Sie einen Skype for Business Server-Onlinehostinganbieter hinzu.
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Beispiel:
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > Sie können nicht mehr als eine Verbundbeziehung mit einem einzelnen Hostinganbieter haben. Wenn Sie also bereits einen Hostinganbieter eingerichtet haben, der eine Verbundbeziehung mit sipfed.online.lync.com hat, fügen Sie keinen anderen Hostinganbieter hinzu, auch wenn die Identität des Hostinganbieters etwas anderes als SkypeOnline ist. 
  
4. Richten Sie den Hostinganbieterverbund zwischen Ihrer Organisation und dem Pushbenachrichtigungsdienst bei Skype for Business Online ein. An der Befehlszeile müssen Sie folgenden Befehl eingeben:
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Aktivieren von Pushbenachrichtigungen

1. Melden Sie sich mit einem Konto an, das Mitglied der **Rolle "CsAdministrator"** ist, auf einem Computer, auf dem **Skype for Business Server Management Shell** und **Ocscore** installiert sind.
    
2. Starten Sie **die Skype for Business Server Management Shell**.
    
3. Aktivieren von Pushbenachrichtigungen:
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Aktivieren des Verbunds:
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>Testen von Verbund- und Pushbenachrichtigungen

1. Melden Sie sich mit einem Konto an, das Mitglied der **Rolle "CsAdministrator"** ist, auf einem Computer, auf dem **Skype for Business Server Management Shell** und **Ocscore** installiert sind.
    
2. Starten Sie **die Skype for Business Server Management Shell**.
    
3. Testen Der Verbundkonfiguration:
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    Beispiel:
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. Testen Sie Ihre Pushbenachrichtigungen:
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    Beispiel:
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>Konfigurieren der Mobilitätsrichtlinie
<a name="ConfigMob"> </a>

Sie können mit Skype for Business Server bestimmen, wer Ihren Mobilitätsdienst, Ihren Anruf per Arbeitsplatz, VoIP (Voice over IP) oder Video verwenden kann, sowie ob WLAN für VoIP oder Video erforderlich ist. Mit "Anrufen über Arbeit" kann ein mobiler Benutzer seine Telefonnummer für die Arbeit anstelle seiner Mobiltelefonnummer beim Platzieren und Empfangen von Anrufen verwenden. Die Person am anderen Ende der Leitung wird die Mobiltelefonnummer des mobilen Benutzers nicht sehen, und dieser mobile Benutzer kann ausgehende Anrufgebühren vermeiden. Wenn VoIP und Video eingerichtet sind, können Benutzer VoIP-Anrufe und Videoanrufe nehmen und machen. Die Einstellungen für die WLAN-Nutzung bestimmen, ob das mobile Gerät eines Benutzers für die Verwendung eines WLAN-Netzwerks über ein Mobilfunkdatennetzwerk erforderlich ist.
  
Mobilität, Anruf über Arbeit sowie die VoIP- und Videofeatures sind standardmäßig aktiviert. Die Einstellung, für die WLAN für VoIP und Video erforderlich ist, ist deaktiviert. Ein Administrator kann dies entweder global, nach Website oder nach Benutzer ändern.
  
Um Mobilitätsfeatures und Anrufe über Die Arbeit verwenden zu können, müssen benutzer:
  
- Aktiviert für Skype for Business Server
    
- Aktiviert für Enterprise-VoIP.
    
- Zugewiesen einer Mobilitätsrichtlinie, für die **die Option EnableMobility** auf **True festgelegt ist.**
    
Damit Benutzer Anrufe über Die Arbeit verwenden können, müssen sie außerdem:
  
- Eine Sprachrichtlinie zugewiesen, für die die Option **Gleichzeitiges Klingeln von Telefonen** aktivieren aktiviert ist.
    
- Zugewiesen einer Mobilitätsrichtlinie, **deren EnableOutsideVoice** auf **True festgelegt ist.**
    
> [!NOTE]
> Benutzer, die nicht für Enterprise-VoIP aktiviert sind, können ihre mobilen Geräte verwenden, um Skype-zu-Skype-VoIP-Anrufe zu führen, oder sie können über den Link Zum Teilnehmen klicken auf ihren mobilen Geräten an Konferenzen teilnehmen, wenn die entsprechenden Optionen für die VoIP-Richtlinie festgelegt sind, der sie zugeordnet sind. Weitere Informationen finden Sie im Thema PLANNING. 
  
### <a name="modify-global-mobility-policy"></a>Ändern der globalen Mobilitätsrichtlinie

1. Melden Sie sich mit einem Konto an, das Mitglied der **Rolle "CsAdministrator"** ist, auf einem Computer, auf dem **Skype for Business Server Management Shell** und **Ocscore** installiert sind.
    
2. Starten Sie **die Skype for Business Server Management Shell**.
    
3. Deaktivieren Sie den Zugriff auf Mobilität und Anruf über Arbeit global, indem Sie Folgendes eingeben:
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Sie können Den Anruf über Die Arbeit deaktivieren, ohne den Zugriff auf Mobilität zu deaktivieren. Sie können Mobilität jedoch nicht deaktivieren, ohne auch Den Anruf über die Arbeit zu deaktivieren. 
  
    Weitere Informationen finden Sie unter [Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-site"></a>Ändern der Mobilitätsrichtlinie nach Website

1. Melden Sie sich mit einem Konto an, das Mitglied der **Rolle "CsAdministrator"** ist, auf einem Computer, auf dem **Skype for Business Server Management Shell** und **Ocscore** installiert sind.
    
2. Starten Sie **die Skype for Business Server Management Shell**.
    
3. Sie können eine Richtlinie auf Websiteebene erstellen, VoIP und Video deaktivieren, WLAN für IP-Audio benötigen und WLAN für IP-Video nach Standort benötigen aktivieren. Typ:
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Weitere Informationen finden Sie [unter New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-user"></a>Ändern der Mobilitätsrichtlinie nach Benutzer

1. Melden Sie sich mit einem Konto an, das Mitglied der **Rolle "CsAdministrator"** ist, auf einem Computer, auf dem **Skype for Business Server Management Shell** und **Ocscore** installiert sind.
    
2. Starten Sie **die Skype for Business Server Management Shell**.
    
3. Erstellen Sie Mobilitätsrichtlinien auf Benutzerebene, und deaktivieren Sie Mobility and Call via Work by user. Typ:
    
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
    > Sie können Den Anruf über Die Arbeit deaktivieren, ohne den Zugriff auf Mobilität zu deaktivieren. Sie können Mobilität jedoch nicht deaktivieren, ohne auch Den Anruf über die Arbeit zu deaktivieren. 
