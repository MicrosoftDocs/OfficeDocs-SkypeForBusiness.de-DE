---
title: Bereitstellen und Konfigurieren der Mobilität für Skype for Business Server
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
description: In diesem Artikel werden Sie durch die Schritte zum Konfigurieren einer vorhandenen Skype for Business Server-Installation für die Verwendung des Mobilitätsdiensts führen, sodass Ihre mobilen Geräte die Vorteile von Skype for Business Server Mobility nutzen können.
ms.openlocfilehash: 420d34dcf1406df776e438e01007770e515c0d4a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820895"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Bereitstellen und Konfigurieren der Mobilität für Skype for Business Server  
 
In diesem Artikel werden Sie durch die Schritte zum Konfigurieren einer vorhandenen Skype for Business Server-Installation für die Verwendung des Mobilitätsdiensts führen, sodass Ihre mobilen Geräte die Vorteile von Skype for Business Server Mobility nutzen können.
  
Nachdem Sie den Artikel ["Plan for Mobility for Skype for Business Server"](../plan-your-deployment/mobility.md) überprüft haben, sollten Sie bereit sein, mit den folgenden Schritten fortzufahren, um Mobilität in Ihrer Skype for Business Server-Umgebung zu implementieren. Die Schritte sind wie folgt (und wir enthalten in dieser Tabelle eine Berechtigungsliste):
  
|**Phase**|**Berechtigungen**|
|:-----|:-----|
|[Erstellen von DNS-Einträgen](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Domänen-Admins  <br/> DNSAdmins  <br/> |
|[Ändern von Zertifikaten](deploy-and-configure-mobility.md#ModCerts) <br/> |Lokaler Administrator  <br/> |
|[Konfigurieren des Reverseproxys](deploy-and-configure-mobility.md#ConfigRP) <br/> |Lokaler Administrator  <br/> |
|[Konfigurieren der AutoErmittlung für Mobilität mit Hybridbereitstellungen](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domänen-Admins  <br/> |
|[Testen der Mobilitätsbereitstellung](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[Konfigurieren von Pushbenachrichtigungen](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[Konfigurieren der Mobilitätsrichtlinie](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
Alle folgenden Abschnitte enthalten Schritte, die davon ausgehen, dass Sie das Planungsthema gelesen haben. Wenn Etwas verwirrend ist, können Sie die Informationen dort einchecken.

> [!NOTE]
> Die McX (Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen mobilen Skype for Business-Clients verwenden bereits unified Communications Web API (UCWA), um Chat, Anwesenheit und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
## <a name="create-dns-records"></a>Erstellen von DNS-Einträgen
<a name="CreateDNSRec"> </a>

Möglicherweise haben Sie diese bereits als Teil Ihrer Skype for Business Server-Umgebung, aber Sie müssen die folgenden Einträge erstellen, damit AutoErmittlung funktioniert:
  
- Ein interner DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung über das Netzwerk Ihrer Organisation herstellen.
    
- Ein externer (oder öffentlicher) DNS-Eintrag zur Unterstützung mobiler Benutzer, die sich von außerhalb des Netzwerks Ihrer Organisation verbinden.
    
Bei diesen Datensätzen kann es sich entweder um A-Namen (Hostnamen) oder um #A0 (Sie müssen nicht beides machen, sondern nur die Schritte für alles hier enthalten).
  
### <a name="create-an-internal-dns-cname-record"></a>Erstellen eines internen DNS-CNAME-Eintrags

1. Melden Sie sich bei einem DNS-Server in Ihrem Netzwerk an, der entweder Mitglied der Gruppe **"Domänen-Admins"** oder **"DnsAdmins"** ist.
    
2. Klicken **Sie auf "Start",**  "Verwaltung auswählen" **(sie** müssen möglicherweise suchen, wenn es sich nicht um eine Option im Startmenü gibt), und klicken Sie dann auf **DNS,** um das DNS-Verwaltungs-Snap-In zu öffnen.
    
3. Im linken Bereich des Konsolenfensters müssen Sie zu der Domäne wechseln, in der sich die Front-End-Server Von Skype for Business Server befinden, und dort die **Forward-Lookupzonen** erweitern.
    
4. Nehmen Sie sich einen Moment Zeit, um zu sehen, welche der folgenden Optionen Sie haben:
    
   - Alle Host-A- oder -AAAA-Einträge für Ihren Front-End-Server (Standard oder Enterprise) oder Front-End-Pool(en).
    
   - Alle Host-A- oder -AAAA-Einträge für einen Director oder Directorpool (eine optionale Konfiguration, die sie möglicherweise in Ihrer Bereitstellung haben).
    
5. Nachdem Sie dies notiert haben, klicken Sie mit der rechten Maustaste auf ihren SIP-Domänennamen, und wählen Sie dann im Menü den neuen **Alias (CNAME)** aus.
    
6. Geben Sie **im Textfeld "Aliasname"** für die interne AutoErmittlungsdienst-URL "lyncdiscoverinternal" als Hostnamen ein.
    
7. Im vollqualifizierten Domänennamen **(FQDN)** für den Zielhost müssen Sie den internen Webdienste-FQDN für Ihren Front-End-Pool (oder einen einzelnen Front-End-Server oder Directorpool oder Director), der in Schritt 4 oben angegeben ist, eingeben oder navigieren. Klicken Sie auf "OK", wenn dieser eingegeben wird.
    
8. Sie müssen einen neuen AutoErmittlungs-CNAME-Eintrag in der #A0 für jede #A1 erstellen, die in Ihrer Skype for Business #A2 unterstützt wird.
    
### <a name="create-an-external-dns-cname-record"></a>Erstellen eines externen DNS-CNAME-Eintrags

1. Diese Schritte sind generisch, da wir nicht wissen können, welchen öffentlichen DNS-Anbieter Sie möglicherweise verwenden, aber wir möchten Sie weiterhin unterstützen. Melden Sie sich bei Ihrem öffentlichen DNS-Anbieter mit einem Konto an, das dort neue DNS-Einträge erstellen kann.
    
2. Zu diesem Zeitpunkt sollte dort bereits eine SIP-Domäne für Skype for Business Server vorhanden sein. Erweitern Sie **die Forward-Lookupzone** für diese SIP-Domäne, oder öffnen Sie sie anderweitig.
    
3. Nehmen Sie sich einen Moment Zeit, um zu sehen, welche der folgenden Optionen Sie haben:
    
   - Alle Host-A- oder -AAAA-Einträge für Ihren Front-End-Server (Standard oder Enterprise) oder Front-End-Pool(en).
    
   - Alle Host-A- oder -AAAA-Einträge für einen Director oder Directorpool (eine optionale Konfiguration, die sie möglicherweise in Ihrer Bereitstellung haben).
    
4. Sobald Sie über diese Informationen verfügen, sollten Sie in der Lage sein, eine Option zum Erstellen eines neuen **Alias (CNAME) auszuwählen.**
    
5. Jetzt sollten Sie einen **Aliasnamen** eingeben können, sie müssen hier lyncdiscover für die externe AutoErmittlungsdienst-URL eingeben.
    
6. Als Nächstes sollte ein Bereich in einen **FQDN** für den Zielhost eingeben werden. Dies muss der FQDN für Ihren Front-End-Pool (oder einzelner Front-End-Server oder Directorpool oder Director), der in Schritt 3 oben angegeben ist.
    
7. Möglicherweise müssen Sie hier speichern, oder wenn Sie zusätzliche #A0 in der #A1 jeder #A2 in Ihrer Skype for Business #A3 erstellen müssen, sollten Sie dies tun, aber sobald Sie bereit sind, speichern Sie Ihre Arbeit.
    
### <a name="create-an-internal-dns-a-record"></a>Erstellen eines internen DNS-A-Eintrags

1. Melden Sie sich bei einem DNS-Server in Ihrem Netzwerk an, der entweder Mitglied der Gruppe **"Domänen-Admins"** oder **"DnsAdmins"** ist.
    
2. Klicken **Sie auf "Start",**  "Verwaltung auswählen" **(sie** müssen möglicherweise suchen, wenn es sich nicht um eine Option im Startmenü gibt), und klicken Sie dann auf **DNS,** um das DNS-Verwaltungs-Snap-In zu öffnen.
    
3. Im linken Bereich des Konsolenfensters müssen Sie zu der Domäne wechseln, in der sich die Front-End-Server Von Skype for Business Server befinden, und dort die **Forward-Lookupzonen** erweitern.
    
4. Nehmen Sie sich einen Moment Zeit, um zu sehen, welche der folgenden Optionen Sie haben:
    
   - Alle Host-A- oder -AAAA-Einträge für Ihren Front-End-Server (Standard oder Enterprise) oder Front-End-Pool(en).
    
   - Alle Host-A- oder -AAAA-Einträge für einen Director oder Directorpool (eine optionale Konfiguration, die sie möglicherweise in Ihrer Bereitstellung haben).
    
5. Nachdem Sie dies notiert haben, klicken Sie mit der rechten Maustaste auf ihren SIP-Domänennamen, und wählen Sie dann im Menü den neuen Host (A oder **AAAA)** aus.
    
6. Geben Sie **im Textfeld "Name"** "lyncdiscoverinternal" als Hostnamen für die interne AutoErmittlungsdienst-URL ein.
    
7. Geben Sie im Textfeld **"IP-Adresse"** die interne Webdienste-IP-Adresse für Ihren Front-End-Pool (oder einen einzelnen Front-End-Server oder Directorpool oder Director) ein, die in Schritt 4 oben angegeben ist.
    
8. Klicken Sie anschließend auf **"Host hinzufügen"** und dann auf **"OK".**
    
9. Sie müssen einen neuen AutoErmittlungs-A- oder -AAAA-Datensatz in der Forward-Lookupzone für jede in Ihrer Skype for Business Server-Umgebung unterstützte SIP-Domäne erstellen. Wiederholen Sie dazu die Schritte 6 bis 8 so oft wie nötig.
    
10. Wenn Sie fertig sind, klicken Sie auf **"Fertig".**
    
### <a name="create-an-external-dns-a-record"></a>Erstellen eines externen DNS-A-Eintrags

1. Diese Schritte sind generisch, da wir nicht wissen können, welchen öffentlichen DNS-Anbieter Sie möglicherweise verwenden, aber wir möchten Sie weiterhin unterstützen. Melden Sie sich bei Ihrem öffentlichen DNS-Anbieter mit einem Konto an, das dort neue DNS-Einträge erstellen kann.
    
2. Zu diesem Zeitpunkt sollte dort bereits eine SIP-Domäne für Skype for Business Server vorhanden sein. Erweitern Sie **die Forward-Lookupzone** für diese SIP-Domäne, oder öffnen Sie sie anderweitig.
    
3. Nehmen Sie sich einen Moment Zeit, um zu sehen, welche der folgenden Optionen Sie haben:
    
   - Alle Host-A- oder -AAAA-Einträge für Ihren Front-End-Server (Standard oder Enterprise) oder Front-End-Pool(en).
    
   - Alle Host-A- oder -AAAA-Einträge für einen Director oder Directorpool (eine optionale Konfiguration, die sie möglicherweise in Ihrer Bereitstellung haben).
    
4. Sobald Sie über diese Informationen verfügen, sollten Sie in der Lage sein, eine Option zum Erstellen eines neuen **Hosts A oder AAAA auszuwählen.**
    
5. Jetzt sollten Sie einen Namen eingeben **können,** sie müssen hier lyncdiscover für die externe AutoErmittlungsdienst-URL eingeben.
    
6. Als Nächstes sollte ein Bereich vorhanden sein, der in eine IP-Adresse ein **muss.** Dabei muss es sich um die IN Schritt 3 identifizierte IP für Ihren Front-End-Pool (oder einen einzelnen Front-End-Server oder Directorpool oder Director) geben.
    
7. Möglicherweise müssen Sie hier speichern, oder wenn Sie zusätzliche A- oder AAAA-Einträge in der Forward-Lookupzone jeder SIP-Domäne für Ihre Skype for Business Server-Umgebung erstellen müssen, sollten Sie dies tun, aber sobald Sie bereit sind, speichern Sie Ihre Arbeit.
    
## <a name="modify-certificates"></a>Ändern von Zertifikaten
<a name="ModCerts"> </a>

Wenn Sie Fragen zur Planung von Zertifikaten haben, haben wir dies in unserem [Artikel "Plan for Mobility for Skype for Business Server"](../plan-your-deployment/mobility.md) dokumentiert. Nachdem Sie dies überprüft haben, werden Sie durch die folgenden Schritte gehen:
  
- Benötigen sie neue Zertifikate?
    
- Anfordern neuer Zertifikate von Ihrer Zertifizierungsstelle
    
- Aktualisieren Ihrer in-Place-Zertifikate mit den Ersetzungen mithilfe von PowerShell.
    
- Überprüfen der Zertifikate mithilfe des Zertifikat-Snap-Ins in der Microsoft Management Console (MMC).
    
### <a name="do-i-need-new-certificates"></a>Benötigen sie neue Zertifikate?

1. Zunächst müssen Sie möglicherweise überprüfen und sehen, welche Zertifikate vor Ort sind und ob sie über die benötigten Einträge verfügen. Dazu müssen Sie sich bei Ihrem Skype for Business Server mit einem Konto anmelden, das ein lokaler Administrator ist. Für einige dieser Schritte muss dieses Konto möglicherweise auch über Rechte für die ausstellende Zertifizierungsstelle verfügen.
    
2. Öffnen Sie die Skype for Business Server-Verwaltungsshell (Sie können die Suche verwenden, um sie zu finden, wenn Sie sie nicht an Das Startmenü oder die Taskleiste angeheftet haben).
    
3. Sie müssen unbedingt wissen, welche Zertifikate zugewiesen wurden, bevor Sie versuchen, ein aktualisiertes Zertifikat hinzufügen. Geben Sie also an dem Befehl folgenden Befehl ein:
    
   ```powershell
   Get-CsCertificate
   ```

4. Die Informationen aus Schritt 3 sind für Sie eindeutig. Sie müssen sie überprüfen, um festzustellen, ob Sie über ein einzelnes Zertifikat verfügen, das für mehrere Dinge zugewiesen wurde, oder ob Ihnen ein anderes Zertifikat für die verschiedenen Komponenten zugewiesen ist, die sie benötigen. Der **Parameter "Use"** gibt Aufzeigt, wie ein Zertifikat verwendet wird, und der Parameter **"Thumbprint"** gibt an, ob es sich um dasselbe Zertifikat oder mehrere Zertifikate gibt.
    
5. Wenn Sie die in unserem Abschnitt "Planung" empfohlenen Einträge für den san-Eintrag haben, sind Sie gut. Wenn nicht, müssen Sie ein neues Zertifikat oder mehrere Zertifikate (je nach Konfiguration) von Ihrer Zertifizierungsstelle anfordern.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>Anfordern eines neuen Zertifikats oder zertifikats von Ihrer Zertifizierungsstelle

1. Nachdem Sie überprüft haben, über welche Einträge sie verfügen, wissen Sie, dass Sie über ein einzelnes Zertifikat verfügen **(nach** der Überprüfung über die obigen Schritte), und Sie haben gelernt, dass Sie nicht über alle benötigten Einträge verfügen. Eine neue Zertifikatanforderung muss an Ihre Zertifizierungsstelle gestellt werden. Öffnen Sie Ihre Skype for Business Server PowerShell:
    
   - Für einen fehlenden AutoErmittlungsdienst-SAN (ersetzen Sie den Parameter "-Ca" durch Ihren eigenen Zertifizierungsstellenpfad):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Wenn Sie nun mehrere SIP-Domänen haben, können Sie den Parameter "AllSipDomain" nicht wie im obigen Beispiel verwenden. Sie müssen stattdessen den Parameter "DomainName" verwenden. Und wenn Sie den Parameter "DomainName" verwenden, müssen Sie den FQDN für die Datensätze "lyncdiscoverinternal" und "lyncdiscover" definieren. Ein Beispiel wäre (ersetzen Sie den Parameter "-Ca" durch Ihren eigenen Pfad der Zertifizierungsstelle):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. Oder nachdem Sie überprüft haben, welche Einträge für den  NSRR Verfügbar sind, haben Sie festgestellt, dass Sie über mehrere Zertifikate verfügen, die nicht über alle benötigten Einträge verfügen. Eine neue Zertifikatanforderung muss an Ihre Zertifizierungsstelle gestellt werden. Öffnen Sie Ihre Skype for Business Server PowerShell:
    
   - Für einen fehlenden AutoErmittlungsdienst-SAN (ersetzen Sie den Parameter "-Ca" durch Ihren eigenen Zertifizierungsstellenpfad):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Wenn Sie nun mehrere SIP-Domänen haben, können Sie den Parameter "AllSipDomain" nicht wie im obigen Beispiel verwenden. Sie müssen stattdessen den Parameter "DomainName" verwenden. Und wenn Sie den Parameter "DomainName" verwenden, müssen Sie den FQDN für die Datensätze "lyncdiscoverinternal" und "lyncdiscover" definieren. Beispiele hierfür sind (Ersetzen des Parameters "-Ca" durch einen eigenen Pfad der Zertifizierungsstelle):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - Nachdem die neuen Zertifikate von der Zertifizierungsstelle generiert wurden, müssen Sie sie zuweisen.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Zuweisen von Zertifikaten mithilfe der Skype for Business Server-Verwaltungsshell

- Je nachdem, was Sie im Abschnitt "Benötigen Sie neue Zertifizierungen" oben gefunden haben, müssen Sie eine **der** folgenden Schritte ausführen.
    
  - Wenn Sie über ein einzelnes Zertifikat für alles verfügen (die Fingerabdrücke sind identisch), müssen Sie dies ausführen:
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - Wenn Sie unterschiedliche Zertifikate für Dinge haben (die Fingerabdrücke unterscheiden sich alle), führen Sie stattdessen dies aus:
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Anzeigen von Zertifikaten in der Microsoft Management Console (MMC)

1. Sie haben die Möglichkeit, Ihre Zertifikate mithilfe des Zertifikat-Snap-Ins für die MMC zu betrachten. Geben Sie einfach MMC in die Suche ein, und es sollte als Anwendungsoption angezeigt werden.
    
2. Zum Hinzufügen des Zertifikat-Snap-Ins müssen Sie auf "Datei" **und** dann auf **"Snap-In hinzufügen/entfernen"** klicken (oder die Tastenkombination **STRG+M** funktioniert). **Zertifikate** sind eine Option im linken Bereich, wählen Sie sie aus, und klicken Sie dann **computerkonto** im Popupfenster, dann **weiter**.
    
3. Bleiben Sie weiterhin im Popupfenster, mit aller Wahrscheinlichkeit tun Sie dies auf dem Computer, auf dem  sich die Zertifikate, die Sie sich anschauen müssen, verwenden. Lassen Sie daher die Auswahl auf dem lokalen Computer, falls ja. Wenn Sie auf einem Remotecomputer arbeiten, ändern Sie das Optionsfeld in einen anderen **Computer,** und  geben Sie dann entweder den FQDN dieses Computers ein, oder verwenden Sie die Schaltfläche "Durchsuchen", um über AD nach diesem Computer zu suchen. Nachdem Sie den Computer ausgewählt haben, müssen Sie auf Fertig stellen klicken, wenn sie bereit sind, und dann **OK,** um das Snap-In der MMC hinzuzufügen. 
    
4. Erweitern Sie **den Abschnitt** "Zertifikate" im linken Bereich der MMC. Erweitern Sie **auch den** Ordner "Persönlich", und wählen Sie dann **"Zertifikate" aus.** Dadurch können Sie die Zertifikate in diesem Speicher sehen.
    
5. Sie müssen das Zertifikat suchen, das Sie anzeigen möchten, mit der rechten Maustaste darauf klicken und öffnen **auswählen.**
    
    > [!NOTE]
    > Wofür wissen Sie, um welches Zertifikat es sich handelt? Es sollte entweder das einzelne Zertifikat sein, das für ihre Farm zugewiesen ist, oder Sie verfügen möglicherweise über mehrere Zertifikate für verschiedene Dinge, z. B. Standard, interne Webdienste usw. In diesem Fall müssen Sie sich möglicherweise mehrere Zertifikate anschauen. Mehrere Zertifikate haben denselben Fingerabdruck. 
  
6. Sobald Sie die Zertifikatansicht angezeigt haben, wählen Sie **Details aus.**  Dadurch wird der Name des Zertifikatssubjekts angezeigt, wenn Sie **"Betreff"** auswählen, und der zugewiesene Betreffname und die zugehörigen Eigenschaften werden angezeigt.
    
7. Sie müssen auch die Einträge für den alternativen **Betreffnamen** überprüfen. Sie finden eine oder mehrere der folgenden Optionen:
    
   - Der Poolname für diesen Pool oder der Name des einzelnen Servers, wenn es sich nicht um einen Pool handelt.
    
   - Der Servername, dem das Zertifikat zugewiesen ist.
    
   - Einfache URL-Einträge, in der Regel "Meet" und "Dialin".
    
   - Interne Webdienste und externe Webdienstenamen (z. B. webpool01.contoso.net, webpool01.contoso.com), basierend auf den Im Topologie-Generator getroffenen Auswahlmöglichkeiten und der Auswahl von überlasteten Webdiensten.
    
   - Wenn bereits zugewiesen, die lyncdiscover.\<sipdomain\> und lyncdiscoverinternal.\<sipdomain\> datensätze.
    
     Sie müssen mehrere Zertifikate überprüfen, wenn Ihnen mehrere Zertifikate zugewiesen sind (siehe Hinweis oben).
    
8. Wenn Sie lyncdiscover finden.\<sipdomain\> und lyncdiscoverinternal.\<sipdomain\> haben Sie dies bereits konfiguriert. Sie können die MMC schließen.
    
9. Wenn sie nicht zugewiesen sind, müssen Sie entweder eine neue Zertifikatanforderung stellen (oben beschrieben) oder sie nach der Anforderung installieren (wir empfehlen hier die oben beschriebene PowerShell).
    
## <a name="configure-the-reverse-proxy"></a>Konfigurieren des Reverseproxys
<a name="ConfigRP"> </a>

Die folgenden Schritte sind nicht dafür gedacht, genau befolgt zu werden. Das liegt daran, dass wir Sie in früheren Versionen des Produkts durch die Konfiguration von Threat Management Gateway (TMG) gegangen wären, und wenn Sie dies nicht verwendet hätten, müssten Sie von dort aus Ihre eigene Version ausarbeiten.
  
TMG wird von Microsoft nicht mehr als Produkt angeboten, und wenn Sie es noch konfigurieren müssen, können Sie sich die [Lync Server 2013-Schritte anschauen.](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx) Die folgenden Informationen sollen jedoch generell hilfreich sein, auch wenn es keine Möglichkeit gibt, bestimmte exemplarische Vorgehensweisen für jeden Reverseproxy zu erstellen.
  
Es gibt zwei wichtige Punkte, die zu berücksichtigen sind:
  
- Werden Sie Ihre anfängliche AutoErmittlungsanforderung über HTTPS (was wir empfehlen) senden?
    
  - Wenn Sie über eine Webveröffentlichungsregel verfügen, müssen Sie sie ändern.
    
  - Wenn Sie noch keine Webveröffentlichungsregel haben, müssen Sie sie erstellen.
    
- Wenn Sie Ihre anfängliche AutoErmittlungsanforderung über HTTP erstellen, müssen Sie auch diese Regel erstellen oder ändern.
    
> [!NOTE]
> **Wichtig** Ein Proxy-Time-Out-Wert ist eine Zahl, die von Bereitstellung zu Bereitstellung unterschiedlich ist. Sie sollten Ihre Bereitstellung überwachen und den Wert für die beste Benutzererfahrung für Clients ändern. Möglicherweise können Sie den Wert auf 200 festlegen. Wenn Sie mobile Lync-Clients in Ihrer Umgebung unterstützen, sollten Sie den Wert auf 960 festlegen, um Pushbenachrichtigungs-Time-Outs von Office 365 zu ermöglichen, die einen Zeitsendwert von 900 haben. Es ist sehr wahrscheinlich, dass Sie den Zeitsendwert erhöhen müssen, um Clientverbindungen zu vermeiden, wenn der Wert zu niedrig ist, oder verringern Sie die Anzahl, wenn Verbindungen über den Proxy nicht getrennt werden, sondern lange nach dem Trennen des Clients wieder löschen. Die Überwachung und Überprüfung der für Ihre Umgebung üblichen Einstellungen ist die einzige genaue Möglichkeit, die entsprechende Einstellung für diesen Wert zu ermitteln.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Ändern der vorhandenen Webveröffentlichungsregel für den externen AUTOErmittlungs-SAN und die URL

1. Öffnen Sie die Reverseproxyschnittstelle.
    
2. Sie müssen die Webveröffentlichungsregel suchen und die Option "Bearbeiten" auswählen (je nach Reverseproxykonfiguration kann sie sich in einem Menü oder auf einer Registerkarte befindet).
    
3. Es sollte ein Bereich verfügbar sein, in dem die Anwendung dieser Webveröffentlichungsregel angezeigt wird. Sie müssen diese Regel für eingehende Websites oder Anforderungen für Websites ändern. Sie fügen einen **neuen** Eintrag hinzu.
    
4. Geben Sie den Namen Ihrer AutoErmittlungswebsite ein (das Beispiel, das wir verwenden, ist lyncdiscover.contoso.com), und klicken Sie abhängig vom Format Ihres Reverseproxys auf **"OK"** oder "Speichern".
    
5. Möglicherweise verfügen Sie über ein neues Zertifikat mit dem AutoErmittlungs-SAN-Eintrag. Dies muss ebenfalls installiert und entsprechend den Einstellungen des Reverseproxys für die Verwendung konfiguriert werden. Achten Sie darauf, alles zu speichern, wenn die Konfiguration abgeschlossen ist.
    
6. Wenn Ihr Reverseproxy über eine **Testfunktionalität** verfügt, verwenden Sie diese, um sicherzustellen, dass alles ordnungsgemäß funktioniert.
    
7. Jetzt müssen Sie diese Schritte möglicherweise wiederholen, wenn Sie einen Director oder Einen Directorpool in Ihrer Umgebung haben (dies würde bedeuten, dass Sie eine zweite Regel haben).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Erstellen einer Webveröffentlichungsregel für die externe AutoErmittlungs-URL

1. Öffnen Sie die Reverseproxyschnittstelle.
    
2. Sie müssen auf der Benutzeroberfläche suchen, wo Sie Ihre  Webveröffentlichungsregeln erstellen, und die Option "Neu" oder "Erstellen" auswählen (je nach Reverseproxykonfiguration kann sie sich in einem Menü oder einer Registerkarte befindet).  Sie suchen nach der Option zum Erstellen einer neuen Webveröffentlichungsregel.
    
3. In der Regel müssen Sie die folgenden Informationen eingeben:
    
   - **Name**: der Name der Regel
    
   - **Regelaktion:** In diesem Fall ist dies eine **"Zulassen"-Regel,** und Sie lassen etwas über Ihren Reverseproxy übergeben.
    
   - Die **Veröffentlichungsregel** oder -option, die Sie auswählen, ist eine einzelne **Website oder ein Lastenausgleich.**
    
   - Dies muss **SSL für** den externen Zugriff sein, wählen Sie diese Option aus.
    
   - Sie müssen einen Pfad für die interne Veröffentlichung veröffentlichen und den FQDN für die externen Webdienste im Lastenausgleich des Front-End-Pools eingeben (oder den FQDN des Lastenausgleichs des Directorpools, wenn Sie einen haben), ein Beispiel wäre sfb_pool01.contoso.local.
    
   - Sie sollten _als den zu veröffentlichende Pfad eingeben, aber Sie müssen auch den ursprünglichen **/\\** Hostheader _*weiterleiten**.
    
   - Es gibt eine Option für **öffentliche oder externe Namensdetails** oder Informationen. Dies ist der Ort, an dem Sie eingeben können:
    
   - **Akzeptiert Anforderungen,** sollte aber für den Domänennamen verwendet werden.
    
   - Geben Sie **für den Namen** **"lyncdiscover" ein.** <sipdomain> (Dies ist die externe AutoErmittlungsdienst-URL). Wenn Sie nun eine Regel für die externe Webdienste-URL im Front-End-Pool erstellen, müssen Sie den FQDN für die externen Webdienste im Front-End-Pool eingeben (z. B. lyncwebextpool01.contoso.com).
    
   - Es wird eine **Pfadoption** geben, und Sie müssen **/\\** hier _eingeben.
    
   - Sie müssen einen _ *SSL Listener** mit Ihrem aktuellen öffentlichen Zertifikat auswählen.
    
   - **Die Authentifizierungsdelegierung** sollte auf **"Keine Delegierung"** festgelegt sein, die direkte Clientauthentifizierung **sollte jedoch** zulässig sein.
    
   - Die Regel sollte auf "Alle **Benutzer" festgelegt werden.**
    
   - Dies sollten alle Informationen sein, die Sie zum Erstellen dieser Regel benötigen, damit Sie fortfahren können.
    
4. Sie müssen sicherstellen, dass der ursprüngliche **Hostheader** weitergeleitet wird.
    
5. Die **Webserverports** müssen ebenfalls festgelegt werden. Gehen Sie wie folgt vor:
    
   - **Umleiten von Anforderungen an den HTTP-Port,** und die Portnummer sollte **8080 sein.**
    
   - **Umleiten von Anforderungen an den SSL-Port,** und die Portnummer sollte **4443 sein.**
    
6. Wenn alles konfiguriert ist, müssen Sie diese speichern oder anwenden und dann die Regel testen.
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>Erstellen einer Webveröffentlichungsregel für Port 80 (optional)

1. Öffnen Sie die Reverseproxyschnittstelle.
    
2. Sie müssen auf der Benutzeroberfläche suchen, wo Sie Ihre  Webveröffentlichungsregeln erstellen, und die Option "Neu" oder "Erstellen" auswählen (je nach Reverseproxykonfiguration kann sie sich in einem Menü oder einer Registerkarte befindet).  Sie suchen nach der Option zum Erstellen einer neuen Webveröffentlichungsregel.
    
3. In der Regel müssen Sie die folgenden Informationen eingeben:
    
   - **Name**: der Name der Regel
    
   - **Regelaktion:** In diesem Fall ist dies eine **"Zulassen"-Regel,** und Sie lassen etwas über Ihren Reverseproxy übergeben.
    
   - Die **Veröffentlichungsregel** oder -option, die Sie auswählen, ist eine einzelne **Website oder ein Lastenausgleich.**
    
   - Dies muss eine nicht gesicherte Verbindung sein, um eine Verbindung mit **dem veröffentlichten Webserver oder der veröffentlichten Farm herzustellen.**
    
   - Sie müssen einen Pfad für die interne Veröffentlichung veröffentlichen und den FQDN für die **VIP-Adresse** des Lastenausgleichs des Front-End-Pools eingeben. Ein Beispiel wäre sfb_pool01.contoso.local.
    
   - Sie sollten _als den zu veröffentlichende Pfad eingeben, aber Sie müssen auch den ursprünglichen **/\\** Hostheader _*weiterleiten**.
    
   - Es gibt eine Option für **öffentliche oder externe Namensdetails** oder Informationen. Dies ist der Ort, an dem Sie eingeben können:
    
   - **Akzeptiert Anforderungen,** sollte aber für den Domänennamen verwendet werden.
    
   - Geben Sie **für den Namen** **"lyncdiscover" ein.** <sipdomain> (Dies ist die externe AutoErmittlungsdienst-URL).
    
   - Es wird eine **Pfadoption** geben, und Sie müssen **/\\** hier _eingeben.
    
   - Sie müssen einen Weblistener auswählen oder Ihrem Reverseproxy erlauben, einen für Sie zu erstellen.
    
   - _ *Authentication Delegation** should be set to No **delegation,** but direct client authentication **should not** be allowed.
    
   - Die Regel sollte auf "Alle **Benutzer" festgelegt werden.**
    
   - Dies sollten alle Informationen sein, die Sie zum Erstellen dieser Regel benötigen, damit Sie fortfahren können.
    
4. Die **Webserverports** müssen festgelegt werden. Gehen Sie wie folgt vor:
    
   - **Umleiten von Anforderungen an den HTTP-Port,** und die Portnummer sollte **8080 sein.**
    
   - **Umleiten von Anforderungen an den SSL-Port,** und die Portnummer sollte **4443 sein.**
    
5. Wenn alles konfiguriert ist, müssen Sie diese speichern oder anwenden und dann die Regel testen.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Konfigurieren der AutoErmittlung für Mobilität mit Hybridbereitstellungen
<a name="ConfigAutoD"> </a>

Hybridumgebungen in Skype for Business Server sind Umgebungen, die eine lokale und eine O365-Umgebung kombinieren. Wenn Skype for Business Server in einer Hybridumgebung funktioniert, muss der AutoErmittlungsdienst in der Lage sein, einen Benutzer aus einer dieser Umgebungen zu finden.
  
Damit mobile Clients ermitteln können, wo sich ein Benutzer befindet, muss der AutoErmittlungsdienst mit einer neuen URL (Uniform Resource Locator) konfiguriert werden. Das sind die Schritte:
  
1. Öffnen Sie die Skype for Business Server-Verwaltungsshell.
    
2. Führen Sie folgendes aus, um den Wert des Attributs **"ProxyFQDN"** für Ihre Skype for Business Server-Umgebung zu erhalten:
    
   ```powershell
   Get-CsHostingProvider
   ```

3. Führen Sie dann, noch im Shellfenster, den
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    Dabei wird [identity] durch den Domänennamen des freigegebenen SIP-Adressraums ersetzt.
    
## <a name="test-your-mobility-deployment"></a>Testen der Mobilitätsbereitstellung
<a name="TestMobility"> </a>

Nachdem Sie den Skype for Business Server Mobility Service und den Skype for Business Server AutoErmittlungsdienst bereitgestellt haben, sollten Sie eine Testtransaktion ausführen, um sicherzustellen, dass Ihre Bereitstellung richtig funktioniert. Sie können **"Test-CsUcwaConference"** ausführen, um zu testen, ob zwei Benutzer eine Konferenz erstellen, an einer Konferenz teilnehmen und mit ihnen kommunizieren können. Sie benötigen zwei Benutzer (real oder test) und ihre vollständigen Anmeldeinformationen, um diese Tests durchführen zu können. Dieser Befehl funktioniert sowohl für Skype for Business-Clients als auch für Lync Server 2013-Clients.
  
Für Lync Server 2010-Clients in Skype for Business Server 2015 müssen Sie **Test-CsMcxP2PIM** zum Testen ausführen. Ihre Lync Server 2010-Benutzer müssen weiterhin tatsächliche Benutzer oder vordefinierte Testbenutzer sein, und Sie benötigen ihre Kennwortanmeldeinformationen.

> [!NOTE]
> Die McX (Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen mobilen Skype for Business-Clients verwenden bereits unified Communications Web API (UCWA), um Chat, Anwesenheit und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Testen von Konferenzen für mobile Skype for Business- und Lync 2013-Clients

1. Melden Sie sich als Mitglied der Rolle **"CsAdministrator"** auf jedem Computer an, auf dem **Skype for Business Server Management Shell** und **Ocscore** installiert sind.
    
2. Starten Sie **die Skype for Business Server-Verwaltungsshell** (Sie können den Namen in die Suche eingeben oder zu **"Alle Programme"** wechseln und ihn auswählen).
    
3. Geben Sie an der Befehlszeile folgenden Befehl ein:
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   Es ist auch möglich, Anmeldeinformationen in einem Skript festgelegt und an das Test-Cmdlet zu übergeben. Nachfolgend finden Sie ein Beispiel dafür.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Testen von Konferenzen für mobile Lync 2010-Clients

> [!NOTE]
> Die McX (Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen mobilen Skype for Business-Clients verwenden bereits unified Communications Web API (UCWA), um Chat, Anwesenheit und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.

1. Melden Sie sich als Mitglied der Rolle **"CsAdministrator"** auf jedem Computer an, auf dem **Skype for Business Server Management Shell** und **Ocscore** installiert sind.
    
2. Starten Sie **die Skype for Business Server-Verwaltungsshell** (Sie können den Namen in die Suche eingeben oder zu **"Alle Programme"** wechseln und ihn auswählen).
    
3. Geben Sie an der Befehlszeile folgenden Befehl ein:
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   Es ist auch möglich, Anmeldeinformationen in einem Skript festgelegt und an das Test-Cmdlet zu übergeben. Nachfolgend finden Sie ein Beispiel dafür.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

Weitere Informationen zu den Befehlsprozeduren finden Sie unter ["Test-CsUcwaConference"](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) und ["Test-CsMcxP2PIM".](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)
  
## <a name="configure-for-push-notifications"></a>Konfigurieren von Pushbenachrichtigungen
<a name="ConfigPush"> </a>

Pushbenachrichtigungen in Form von Signalen, Symbolen oder Warnungen können auch dann an ein mobiles Gerät gesendet werden, wenn die Skype- oder Lync-App inaktiv ist. Aber was sind Pushbenachrichtigungen? Dabei handelt es sich um Ereigniswarnungen, z. B. eine neue oder verpasste Sofortnachrichteneinladung oder für eine empfangene Voicemail. Der Skype for Business Server -Mobilitätsdienst sendet diese Benachrichtigungen an den cloudbasierten Skype for Business Server-Pushbenachrichtigungsdienst, der dann die Benachrichtigungen an den Microsoft Push Notification Service (MSNS) für Windows Phone sendet.
  
Diese Funktionalität ist gegenüber Lync Server 2013 unverändert, aber wenn Sie über einen Skype for Business Server verfügen, sollten Sie die folgenden Schritte unternehmen:
  
- Fügen Sie für einen Skype for Business Server-Edgeserver einen neuen Hostinganbieter, Microsoft Skype for Business Online, hinzu, und richten Sie dann einen Hostinganbieterverbund zwischen Ihrer Organisation und Skype for Business Online ein.
    
- Aktivieren Sie Pushbenachrichtigungen, indem Sie das **Cmdlet "Set-CsPushNotificationConfiguration"** ausführen. Pushbenachrichtigungen sind standardmäßig deaktiviert.
    
- Testen Sie die Verbundkonfiguration und Pushbenachrichtigungen.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Konfigurieren Ihres Skype for Business-Edgeservers für Pushbenachrichtigungen

1. Melden Sie sich mit einem Konto, das Mitglied der Rolle **"CsAdministrator"** ist, an einem Computer an, auf dem **Skype for Business Server Management Shell** und **Ocscore** installiert sind.
    
2. Starten Sie **die Skype for Business Server-Verwaltungsshell.**
    
3. Fügen Sie einen Skype for Business Server-Onlinehostinganbieter hinzu.
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Beispiel:
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > Sie können nicht mehr als eine Verbundbeziehung mit einem einzigen Hostinganbieter haben. Wenn Sie also bereits einen Hostinganbieter eingerichtet haben, der eine Verbundbeziehung mit sipfed.online.lync.com hat, fügen Sie keinen weiteren Hostinganbieter hinzu, auch wenn die Identität des Hostinganbieters etwas anderes als SkypeOnline ist. 
  
4. Richten Sie den Hostinganbieterverbund zwischen Ihrer Organisation und dem Pushbenachrichtigungsdienst bei Skype for Business Online ein. Geben Sie an der Befehlszeile folgenden Befehl ein:
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Aktivieren von Pushbenachrichtigungen

1. Melden Sie sich mit einem Konto, das Mitglied der Rolle **"CsAdministrator"** ist, an einem Computer an, auf dem **Skype for Business Server Management Shell** und **Ocscore** installiert sind.
    
2. Starten Sie **die Skype for Business Server-Verwaltungsshell.**
    
3. Aktivieren Sie Pushbenachrichtigungen:
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Aktivieren Sie den Verbund:
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>Testen von Verbund- und Pushbenachrichtigungen

1. Melden Sie sich mit einem Konto, das Mitglied der Rolle **"CsAdministrator"** ist, an einem Computer an, auf dem **Skype for Business Server Management Shell** und **Ocscore** installiert sind.
    
2. Starten Sie **die Skype for Business Server-Verwaltungsshell.**
    
3. Testen Sie die Verbundkonfiguration:
    
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

Sie können mit Skype for Business Server bestimmen, wer Ihren Mobilitätsdienst, Geschäft geschäftig, VoIP (Voice over IP) oder Video verwenden kann und ob für VoIP oder Video WLAN erforderlich ist. "Anruf über Arbeit" ermöglicht es einem mobilen Benutzer, seine Arbeitstelefonnummer anstelle seiner Mobiltelefonnummer beim Ein- und Entgegenstellen von Anrufen zu verwenden. Die Person am anderen Ende der Leitung sieht die Mobiltelefonnummer des mobilen Benutzers nicht und ermöglicht es diesem mobilen Benutzer, ausgehende Anrufgebühren zu vermeiden. Wenn VoIP und Video eingerichtet sind, können Benutzer VoIP-Anrufe und -Videos nutzen und machen. Die Einstellungen für die WLAN-Nutzung bestimmen, ob das mobile Gerät eines Benutzers für die Verwendung eines WLAN-Netzwerks über ein Mobilfunknetz erforderlich ist.
  
Mobilität, Anruf über Arbeit sowie die VoIP- und Videofunktionen sind standardmäßig aktiviert. Die Einstellung zum Erfordern von WLAN für VoIP und Video ist deaktiviert. Ein Administrator kann dies entweder global, nach Standort oder nach Benutzer ändern.
  
Um Mobilitätsfeatures und "Anruf über Arbeit" verwenden zu können, müssen benutzer:
  
- Aktiviert für Skype for Business Server
    
- Aktiviert für Enterprise-VoIP.
    
- Zugewiesen einer Mobilitätsrichtlinie, für die die Option **"EnableMobility"** auf **"True" festgelegt ist.**
    
Damit Benutzer "Anruf über Arbeit" verwenden können, müssen sie auch:
  
- Zugewiesene Sprachrichtlinie, für die die Option **"Gleichzeitiges Klingeln von Telefonen** aktivieren" aktiviert ist.
    
- Zugewiesen einer Mobilitätsrichtlinie, für die **"EnableOutsideVoice"** auf **"True" festgelegt ist.**
    
> [!NOTE]
> Benutzer, die nicht für Enterprise-VoIP aktiviert sind, können ihre mobilen Geräte verwenden, um Skype-zu-Skype-VoIP-Anrufe zu führen, oder sie können über den Link "Zum Beitreten klicken" auf ihren mobilen Geräten an Konferenzen teilnehmen, wenn die entsprechenden Optionen für die VoIP-Richtlinie festgelegt sind, der sie zugeordnet sind. Das Planungsthema enthält weitere Details. 
  
### <a name="modify-global-mobility-policy"></a>Ändern der globalen Mobilitätsrichtlinie

1. Melden Sie sich mit einem Konto, das Mitglied der Rolle **"CsAdministrator"** ist, an einem Computer an, auf dem **Skype for Business Server Management Shell** und **Ocscore** installiert sind.
    
2. Starten Sie **die Skype for Business Server-Verwaltungsshell.**
    
3. Deaktivieren Sie den Zugriff auf Mobilität und Anruf über Arbeit global, indem Sie Folgendes eingeben:
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Sie können "Anruf über Arbeit" deaktivieren, ohne den Zugriff auf Mobilität zu deaktivieren. Sie können die Mobilität jedoch nicht deaktivieren, ohne auch "Anruf über Arbeit" zu deaktivieren. 
  
    Weitere Informationen finden Sie unter [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-site"></a>Ändern der Mobilitätsrichtlinie nach Standort

1. Melden Sie sich mit einem Konto, das Mitglied der Rolle **"CsAdministrator"** ist, an einem Computer an, auf dem **Skype for Business Server Management Shell** und **Ocscore** installiert sind.
    
2. Starten Sie **die Skype for Business Server-Verwaltungsshell.**
    
3. Sie können eine Richtlinie auf Standortebene erstellen, VoIP und Video deaktivieren, WLAN für IP-Audio und WLAN für IP-Video nach Standort aktivieren. Typ:
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Weitere Informationen finden Sie unter [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-user"></a>Ändern der Mobilitätsrichtlinie nach Benutzer

1. Melden Sie sich mit einem Konto, das Mitglied der Rolle **"CsAdministrator"** ist, an einem Computer an, auf dem **Skype for Business Server Management Shell** und **Ocscore** installiert sind.
    
2. Starten Sie **die Skype for Business Server-Verwaltungsshell.**
    
3. Erstellen Sie Mobilitätsrichtlinien auf Benutzerebene, und deaktivieren Sie "Mobilität und Anruf über Arbeit" nach Benutzer. Typ:
    
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
    > Sie können "Anruf über Arbeit" deaktivieren, ohne den Zugriff auf Mobilität zu deaktivieren. Sie können die Mobilität jedoch nicht deaktivieren, ohne auch "Anruf über Arbeit" zu deaktivieren. 
  

