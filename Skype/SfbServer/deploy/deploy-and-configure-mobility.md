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
ms.localizationpriority: medium
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Dieser Artikel führt Sie durch die Schritte zum Konfigurieren einer vorhandenen Skype for Business Server-Installation für die Verwendung des Mobilitätsdiensts, damit Ihre mobilen Geräte Skype for Business Server Mobilitätsfeatures nutzen können.
ms.openlocfilehash: c0b8a3e2902a8605f952683d6a3629af9e075798
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611334"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Bereitstellen und Konfigurieren der Mobilität für Skype for Business Server  
 
Dieser Artikel führt Sie durch die Schritte zum Konfigurieren einer vorhandenen Skype for Business Server-Installation für die Verwendung des Mobilitätsdiensts, damit Ihre mobilen Geräte Skype for Business Server Mobilitätsfeatures nutzen können.
  
Nachdem Sie den Artikel ["Plan for Mobility for Skype for Business Server"](../plan-your-deployment/mobility.md) gelesen haben, sollten Sie bereit sein, mit den folgenden Schritten fortzufahren, um Mobilität in Ihrer Skype for Business Server Umgebung bereitzustellen. Die Schritte sind wie folgt (und wir nehmen in dieser Tabelle eine Berechtigungsliste auf):
  
|**Phase**|**Berechtigungen**|
|:-----|:-----|
|[Erstellen von DNS-Einträgen](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Domänen-Admins  <br/> DNSAdmins  <br/> |
|[Ändern von Zertifikaten](deploy-and-configure-mobility.md#ModCerts) <br/> |Lokaler Administrator  <br/> |
|[Konfigurieren des Reverseproxys](deploy-and-configure-mobility.md#ConfigRP) <br/> |Lokaler Administrator  <br/> |
|[Konfigurieren der AutoErmittlung für Mobilität mit Hybridbereitstellungen](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domänen-Admins  <br/> |
|[Testen der Mobilitätsbereitstellung](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[Konfigurieren von Pushbenachrichtigungen](deploy-and-configure-mobility.md#ConfigPush) <br/> |Rtcuniversalserveradmins  <br/> |
|[Konfigurieren der Mobilitätsrichtlinie](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
Alle folgenden Abschnitte enthalten Schritte, bei denen davon ausgegangen wird, dass Sie das Planungsthema gelesen haben. Wenn Sie etwas verwirrend finden, können Sie sich die Informationen dort ansehen.

> [!NOTE]
> McX(Mobility Service)-Unterstützung für mobile Legacyclients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen Skype for Business mobile Clients verwenden bereits unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.
  
## <a name="create-dns-records"></a>Erstellen von DNS-Einträgen
<a name="CreateDNSRec"> </a>

Möglicherweise verfügen Sie bereits über diese als Teil Ihrer Skype for Business Server Umgebung, aber Sie müssen die folgenden Datensätze erstellen, damit AutoDiscovery funktioniert:
  
- Ein interner DNS-Eintrag zur Unterstützung mobiler Benutzer, die innerhalb des Netzwerks Ihrer Organisation eine Verbindung herstellen.
    
- Ein externer (oder öffentlicher) DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung von außerhalb des Netzwerks Ihrer Organisation herstellen.
    
Bei diesen Datensätzen kann es sich um A-Namen (Hostnamen) oder CNAME-Einträge (sie müssen nicht beides vornehmen, wir fügen nur die Schritte für alles hier ein).
  
### <a name="create-an-internal-dns-cname-record"></a>Erstellen eines internen DNS-CNAME-Eintrags

1. Melden Sie sich bei einem DNS-Server in Ihrem Netzwerk an, der entweder Mitglied der Gruppe **"Domänenadministratoren"** oder **"DnsAdmins"** ist.
    
2. Klicken Sie auf **"Start",** **"Administrative Tools"** (Sie müssen möglicherweise **danach suchen,** wenn es sich nicht um eine Option aus dem Startmenü handelt), und klicken Sie dann auf **DNS,** um das DNS-Administrator-Snap-In zu öffnen.
    
3. Im linken Bereich des Konsolenfensters müssen Sie zu der Domäne wechseln, in der sich die Front-End-Server Ihrer Skype for Business Server befinden, und die **Forward-Lookupzonen** dort erweitern.
    
4. Nehmen Sie sich einen Moment Zeit, um zu sehen, welche der folgenden Optionen Sie haben:
    
   - Alle Host-A- oder AAAA-Einträge für Ihren Front-End-Server (Standard oder Enterprise) oder Front-End-Pools.
    
   - Alle Host-A- oder AAAA-Einträge für einen Director- oder Director-Pool (eine optionale Konfiguration, die Möglicherweise in Ihrer Bereitstellung vorhanden ist).
    
5. Nachdem Sie dies notiert haben, klicken Sie mit der rechten Maustaste auf Ihren SIP-Domänennamen, und wählen Sie dann im Menü **"Neuer Alias (CNAME)"** aus.
    
6. Geben Sie im Textfeld **"Aliasname"** "lyncdiscoverinternal" als Hostnamen für die interne AutoErmittlungsdienst-URL ein.
    
7. Im **vollqualifizierten Domänennamen (FQDN für den Zielhost)** müssen Sie den internen Webdienst-FQDN für Ihren Front-End-Pool (oder einen einzelnen Front-End-Server oder Directorpool oder Director) eingeben oder navigieren, der in Schritt 4 oben angegeben ist. Klicken Sie auf "OK", wenn sie eingegeben wird.
    
8. Sie müssen einen neuen AutoErmittlungs-CNAME-Eintrag in der Forward-Lookupzone für jede SIP-Domäne erstellen, die in Ihrer Skype for Business Server-Umgebung unterstützt wird.
    
### <a name="create-an-external-dns-cname-record"></a>Erstellen eines externen DNS-CNAME-Eintrags

1. Diese Schritte sind generisch, da wir nicht wissen können, welchen öffentlichen DNS-Anbieter Sie möglicherweise verwenden, aber wir möchten Ihnen weiterhin helfen. Melden Sie sich bei Ihrem öffentlichen DNS-Anbieter mit einem Konto an, das dort neue DNS-Einträge erstellen kann.
    
2. Zu diesem Zeitpunkt sollte bereits eine SIP-Domäne für Skype for Business Server vorhanden sein. Erweitern Sie die **Forward-Lookupzone** für diese SIP-Domäne, oder öffnen Sie sie anderweitig.
    
3. Nehmen Sie sich einen Moment Zeit, um zu sehen, welche der folgenden Optionen Sie haben:
    
   - Alle Host-A- oder AAAA-Einträge für Ihren Front-End-Server (Standard oder Enterprise) oder Front-End-Pools.
    
   - Alle Host-A- oder AAAA-Einträge für einen Director- oder Director-Pool (eine optionale Konfiguration, die Möglicherweise in Ihrer Bereitstellung vorhanden ist).
    
4. Sobald Sie über diese Informationen verfügen, sollten Sie in der Lage sein, eine Option zum Erstellen eines **neuen Alias (CNAME)** auszuwählen.
    
5. Jetzt sollten Sie in der Lage sein, einen **Aliasnamen** einzugeben. Sie müssen hier "lyncdiscover" für die externe AutoErmittlungsdienst-URL eingeben.
    
6. Als Nächstes sollte ein Bereich vorhanden sein, in den ein **FQDN für den Zielhost** eingegeben werden kann. Dies muss der FQDN für Ihren Front-End-Pool (oder einen einzelnen Front-End-Server oder Directorpool oder Director) sein, der in Schritt 3 oben angegeben ist.
    
7. Möglicherweise müssen Sie hier speichern, oder wenn Sie zusätzliche CNAME-Einträge in der Forward-Lookupzone jeder SIP-Domäne in Ihrer Skype for Business Server Umgebung erstellen müssen, sollten Sie dies tun, aber sobald Sie fertig sind, speichern Sie Ihre Arbeit.
    
### <a name="create-an-internal-dns-a-record"></a>Erstellen eines internen DNS A-Eintrags

1. Melden Sie sich bei einem DNS-Server in Ihrem Netzwerk an, der entweder Mitglied der Gruppe **"Domänenadministratoren"** oder **"DnsAdmins"** ist.
    
2. Klicken Sie auf **"Start",** **"Administrative Tools"** (Sie müssen möglicherweise **danach suchen,** wenn es sich nicht um eine Option aus dem Startmenü handelt), und klicken Sie dann auf **DNS,** um das DNS-Administrator-Snap-In zu öffnen.
    
3. Im linken Bereich des Konsolenfensters müssen Sie zu der Domäne wechseln, in der sich die Front-End-Server Ihrer Skype for Business Server befinden, und die **Forward-Lookupzonen** dort erweitern.
    
4. Nehmen Sie sich einen Moment Zeit, um zu sehen, welche der folgenden Optionen Sie haben:
    
   - Alle Host-A- oder AAAA-Einträge für Ihren Front-End-Server (Standard oder Enterprise) oder Front-End-Pools.
    
   - Alle Host-A- oder AAAA-Einträge für einen Director- oder Director-Pool (eine optionale Konfiguration, die Möglicherweise in Ihrer Bereitstellung vorhanden ist).
    
5. Nachdem Sie dies notiert haben, klicken Sie mit der rechten Maustaste auf Ihren SIP-Domänennamen, und wählen Sie dann im Menü **"Neuer Host " (A oder AAAA)** aus.
    
6. Geben Sie im Textfeld **"Name"** "lyncdiscoverinternal" als Hostnamen für die interne AutoErmittlungsdienst-URL ein.
    
7. Geben Sie im Textfeld **"IP-Adresse"** die interne Webdienst-IP-Adresse für Ihren Front-End-Pool (oder einen einzelnen Front-End-Server oder Directorpool oder Director) ein, der in Schritt 4 oben angegeben ist.
    
8. Klicken Sie dann auf **"Host hinzufügen"** und dann auf **"OK".**
    
9. Sie müssen eine neue AutoErmittlung A- oder AAAA-Einträge in der Forward-Lookupzone für jede SIP-Domäne erstellen, die in Ihrer Skype for Business Server-Umgebung unterstützt wird. Wiederholen Sie dazu die Schritte 6 bis 8 so oft wie nötig.
    
10. Wenn Sie fertig sind, klicken Sie auf **"Fertig".**
    
### <a name="create-an-external-dns-a-record"></a>Erstellen eines externen DNS A-Eintrags

1. Diese Schritte sind generisch, da wir nicht wissen können, welchen öffentlichen DNS-Anbieter Sie möglicherweise verwenden, aber wir möchten Ihnen weiterhin helfen. Melden Sie sich bei Ihrem öffentlichen DNS-Anbieter mit einem Konto an, das dort neue DNS-Einträge erstellen kann.
    
2. Zu diesem Zeitpunkt sollte bereits eine SIP-Domäne für Skype for Business Server vorhanden sein. Erweitern Sie die **Forward-Lookupzone** für diese SIP-Domäne, oder öffnen Sie sie anderweitig.
    
3. Nehmen Sie sich einen Moment Zeit, um zu sehen, welche der folgenden Optionen Sie haben:
    
   - Alle Host-A- oder AAAA-Einträge für Ihren Front-End-Server (Standard oder Enterprise) oder Front-End-Pools.
    
   - Alle Host-A- oder AAAA-Einträge für einen Director- oder Director-Pool (eine optionale Konfiguration, die Möglicherweise in Ihrer Bereitstellung vorhanden ist).
    
4. Sobald Sie über diese Informationen verfügen, sollten Sie in der Lage sein, eine Option zum Erstellen eines **neuen Hosts A oder AAAA** auszuwählen.
    
5. Jetzt sollten Sie in der Lage sein, einen **Namen** einzugeben. Sie müssen hier "lyncdiscover" für die externe AutoErmittlungsdienst-URL eingeben.
    
6. Als Nächstes sollte ein Bereich vorhanden sein, der in eine **IP-Adresse** eingegeben werden kann. Dies muss die IP für Ihren Front-End-Pool (oder einen einzelnen Front-End-Server oder Directorpool oder Director) sein, der in Schritt 3 oben angegeben ist.
    
7. Möglicherweise müssen Sie hier speichern, oder wenn Sie zusätzliche A- oder AAAA-Einträge in der Forward-Lookupzone jeder SIP-Domäne für Ihre Skype for Business Server Umgebung erstellen müssen, sollten Sie dies tun, aber sobald Sie bereit sind, speichern Sie Ihre Arbeit.
    
## <a name="modify-certificates"></a>Ändern von Zertifikaten
<a name="ModCerts"> </a>

Wenn Sie Fragen zur Planung von Zertifikaten haben, haben wir dies in unserem Artikel ["Plan for Mobility for Skype for Business Server"](../plan-your-deployment/mobility.md) dokumentiert. Nachdem Sie dies überprüft haben, führen wir Sie durch Folgendes:
  
- Benötisiere ich neue Zertifikate?
    
- Anfordern neuer Zertifikate von Ihrer Zertifizierungsstelle
    
- Aktualisieren Ihrer direkten Zertifikate mit den Ersetzungen mithilfe von PowerShell.
    
- Überprüfen der Zertifikate mithilfe des Snap-Ins "Zertifikate" in der Microsoft Management Console (MMC).
    
### <a name="do-i-need-new-certificates"></a>Benötisiere ich neue Zertifikate?

1. Zunächst müssen Sie möglicherweise überprüfen, welche Zertifikate vorhanden sind und ob sie über die benötigten Einträge verfügen. Dazu müssen Sie sich bei Ihrem Skype for Business Server mit einem Konto anmelden, das ein lokaler Administrator ist. Für einige dieser Schritte muss dieses Konto möglicherweise auch über Rechte für die ausstellende Zertifizierungsstelle verfügen.
    
2. Öffnen Sie die Skype for Business Server-Verwaltungsshell (Sie können die Suche verwenden, um sie zu finden, wenn Sie sie nicht an Ihre Startmenü oder Taskleiste angeheftet haben).
    
3. Es ist wichtig, dass Sie wissen, welche Zertifikate zugewiesen wurden, bevor Sie versuchen, ein aktualisiertes Zertifikat hinzuzufügen. Geben Sie also am Befehl Folgendes ein:
    
   ```powershell
   Get-CsCertificate
   ```

4. Die Informationen aus Schritt 3 sind für Sie eindeutig. Sie müssen es durchsehen, um festzustellen, ob Sie über ein einzelnes Zertifikat verfügen, das für mehrere Dinge zugewiesen wurde, oder ob Ihnen für die verschiedenen Komponenten, die sie benötigen, ein anderes Zertifikat zugewiesen wurde. Mit dem Parameter **"Use"** erfahren Sie, wie ein Zertifikat verwendet wird, und der **Parameter "Thumbprint"** teilt Ihnen mit, ob es sich um dasselbe Zertifikat oder mehrere Zertifikate handelt.
    
5. Wenn Sie die in unserem Planungsabschnitt empfohlenen SAN-Einträge haben, sind Sie gut. Wenn dies nicht der Fall ist, müssen Sie ein neues Zertifikat oder mehrere Zertifikate (je nach Konfiguration) von Ihrer Zertifizierungsstelle anfordern.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>Anfordern eines neuen Zertifikats oder zertifikats von Ihrer Zertifizierungsstelle

1. Nachdem Sie überprüft haben, welche SAN-Einträge Sie haben, wissen Sie, dass Sie über ein **einzelnes Zertifikat** verfügen (nach der Überprüfung über die obigen Schritte), und Sie haben gelernt, dass Sie nicht über alle benötigten Einträge verfügen. Eine neue Zertifikatanforderung muss an Ihre Zertifizierungsstelle gestellt werden. Öffnen Sie Ihre Skype for Business Server PowerShell:
    
   - Für einen fehlenden AutoErmittlungsdienst-SAN (ersetzen Sie den Parameter -Ca durch Ihren eigenen Zertifizierungsstellenpfad):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Wenn Sie nun über mehrere SIP-Domänen verfügen, können Sie den Parameter "AllSipDomain" nicht wie im obigen Beispiel verwenden. Sie müssen stattdessen den Parameter "DomainName" verwenden. Und wenn Sie den Parameter "DomainName" verwenden, müssen Sie den FQDN für die lyncdiscoverinternal- und lyncdiscover-Datensätze definieren. Ein Beispiel wäre (ersetzen Sie den Parameter "-Ca" durch Ihren eigenen Zertifizierungsstellenpfad):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. Oder nachdem Sie überprüft haben, welche SAN-Einträge Sie haben, haben Sie **festgestellt,** dass Sie über mehrere Zertifikate verfügen, die nicht über alle benötigten Einträge verfügen. Eine neue Zertifikatanforderung muss an Ihre Zertifizierungsstelle gestellt werden. Öffnen Sie Ihre Skype for Business Server PowerShell:
    
   - Für einen fehlenden AutoErmittlungsdienst-SAN (ersetzen Sie den Parameter -Ca durch Ihren eigenen Zertifizierungsstellenpfad):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Wenn Sie nun über mehrere SIP-Domänen verfügen, können Sie den Parameter "AllSipDomain" nicht wie im obigen Beispiel verwenden. Sie müssen stattdessen den Parameter "DomainName" verwenden. Und wenn Sie den Parameter "DomainName" verwenden, müssen Sie den FQDN für die lyncdiscoverinternal- und lyncdiscover-Datensätze definieren. Beispiele hierfür sind (Ersetzen des Parameters "-Ca" durch ihren eigenen Zertifizierungsstellenpfad):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - Nachdem die neuen Zertifikate von der Zertifizierungsstelle generiert wurden, müssen Sie sie zuweisen.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Zuweisen von Zertifikaten mithilfe Skype for Business Server Verwaltungsshell

- Je nachdem, was Sie im Abschnitt "Benötigen neuer Zertifizierungen" oben gefunden haben, müssen Sie **eine** der folgenden Schritte ausführen.
    
  - Wenn Sie über ein einzelnes Zertifikat für alles verfügen (die Fingerabdrücke sind identisch), müssen Sie Folgendes ausführen:
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - Wenn Sie unterschiedliche Zertifikate für Dinge haben (die Fingerabdrücke sind alle unterschiedlich), führen Sie stattdessen Folgendes aus:
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Anzeigen von Zertifikaten in der Microsoft Management Console (MMC)

1. Sie haben die Möglichkeit, Ihre Zertifikate mithilfe des Zertifikat-Snap-Ins für mmc anzusehen. Geben Sie einfach MMC in die Suche ein, und es sollte als Anwendungsoption angezeigt werden.
    
2. Um das Zertifikat-Snap-In hinzuzufügen, müssen Sie auf **"Datei"** klicken und dann **"Snap-In hinzufügen/entfernen"...** (oder die Tastenkombination **STRG+M** funktioniert ebenfalls). **Zertifikate** sind eine Option im linken Bereich, wählen Sie sie aus, und klicken Sie dann im Popupfenster auf **"Computerkonto",** und klicken Sie dann auf **"Weiter".**
    
3. Auch im Popupfenster tun Sie dies wahrscheinlich auf dem Computer, auf dem sich die Zertifikate befinden, die Sie sich ansehen müssen. Behalten Sie daher die Auswahl auf dem **lokalen Computer** bei, wenn dies der Fall ist. Wenn Sie auf einem Remotecomputer arbeiten, ändern Sie das Optionsfeld in **einen anderen Computer,** und geben Sie dann entweder den FQDN dieses Computers ein, oder verwenden Sie die Schaltfläche **"Durchsuchen",** um über AD nach diesem Computer zu suchen. Nachdem Sie den Computer ausgewählt haben, müssen Sie auf **Fertig stellen** klicken, und klicken Sie dann auf **OK,** um das Snap-In zur MMC hinzuzufügen.
    
4. Erweitern Sie den Abschnitt **"Zertifikate"** im linken Bereich des MMC. Erweitern Sie auch den **persönlichen** Ordner, und wählen Sie dann **Zertifikate** aus. Auf diese Weise können Sie die Zertifikate in diesem Speicher anzeigen.
    
5. Sie müssen das Zertifikat suchen, das Sie anzeigen möchten, mit der rechten Maustaste darauf klicken und **"Öffnen"** auswählen.
    
    > [!NOTE]
    > Woher wissen Sie, um welches Zertifikat es sich handelt? Es sollte entweder das einzelne Zertifikat sein, das allen Für Ihre Farm zugewiesen ist, oder Sie verfügen möglicherweise über mehrere Zertifikate für verschiedene Dinge, z. B. Standard, interne Webdienste usw.. In diesem Fall müssen Sie sich möglicherweise mehrere Zertifikate ansehen. Mehrere Zertifikate haben den gleichen Fingerabdruck. 
  
6. Nachdem Sie zur **Zertifikatansicht** gelangt sind, wählen Sie **Details** aus. Dadurch wird der Zertifikatantragstellername angezeigt, wenn Sie **"Betreff"** auswählen, und der zugewiesene Antragstellername und die zugehörigen Eigenschaften werden angezeigt.
    
7. Sie müssen auch die Einträge für **alternative Antragstellernamen** überprüfen. Sie finden eine oder mehrere der folgenden Optionen:
    
   - Der Poolname für diesen Pool oder der Name des einzelnen Servers, wenn es sich nicht um einen Pool handelt.
    
   - Der Servername, dem das Zertifikat zugewiesen ist.
    
   - Einfache URL-Einträge, in der Regel "Meet" und "Dialin".
    
   - Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.
    
   - Wenn die LyncDiscover bereits zugewiesen ist.\<sipdomain\> und lyncdiscoverinternal.\<sipdomain\> Datensätze.
    
     Wenn Mehrere Zertifikate zugewiesen sind, müssen Sie mehrere Zertifikate überprüfen (siehe Hinweis oben).
    
8. Wenn Sie also lyncdiscover finden.\<sipdomain\> und lyncdiscoverinternal.\<sipdomain\> Records, you've got this configured already. Sie können mmc schließen.
    
9. Wenn sie nicht zugewiesen sind, müssen Sie entweder eine neue Zertifikatanforderung (oben beschrieben) oder sie nach der Anforderung installieren (wir empfehlen die folgende PowerShell oben).
    
## <a name="configure-the-reverse-proxy"></a>Konfigurieren des Reverseproxys
<a name="ConfigRP"> </a>

Die folgenden Schritte sollten nicht genau befolgt werden. Das liegt daran, dass wir Sie in früheren Versionen des Produkts durch die Konfiguration von Threat Management Gateway (TMG) geführt haben, und wenn Sie dies nicht verwenden würden, müssten Sie von dort aus Eine eigene Version ausarbeiten.
  
TMG wird von Microsoft nicht mehr als Produkt angeboten, und wenn Sie es noch konfigurieren müssen, können Sie sich die Schritte zu [Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-the-reverse-proxy-for-mobility)ansehen. Die folgenden Informationen sollen jedoch generell hilfreicher sein, auch wenn es keine Möglichkeit gibt, spezifische exemplarische Vorgehensweisen für jeden Reverseproxy bereitzustellen.
  
Es gibt zwei Hauptaspekte, die Sie berücksichtigen sollten:
  
- Führen Sie Ihre anfängliche AutoErmittlungsanforderung über HTTPS durch (was wir empfehlen)?
    
  - Wenn Sie über eine Webveröffentlichungsregel verfügen, müssen Sie sie ändern.
    
  - Wenn Sie noch keine Webveröffentlichungsregel haben, müssen Sie sie erstellen.
    
- Wenn Sie Ihre anfängliche AutoErmittlungsanforderung über HTTP durchführen, müssen Sie auch diese Regel erstellen oder ändern.
    
> [!NOTE]
> **Wichtig** Ein Proxytimeoutwert ist eine Zahl, die von Bereitstellung zu Bereitstellung unterschiedlich ist. Sie sollten Ihre Bereitstellung überwachen und den Wert für eine optimale Benutzererfahrung für Clients ändern. Möglicherweise können Sie den Wert auf 200 festlegen. Wenn Sie mobile Lync-Clients in Ihrer Umgebung unterstützen, sollten Sie den Wert auf 960 festlegen, um Timeouts für Pushbenachrichtigungen von Office 365 zuzulassen, die einen Timeoutwert von 900 aufweisen. Es ist sehr wahrscheinlich, dass Sie den Timeoutwert erhöhen müssen, um zu vermeiden, dass die Clientverbindung getrennt wird, wenn der Wert zu niedrig ist, oder die Anzahl verringert wird, wenn Verbindungen über den Proxy lange nach dem Trennen des Clients nicht getrennt, sondern gelöscht werden. Die Überwachung und Überprüfung, was für Ihre Umgebung üblich ist, ist die einzige genaue Methode, um die entsprechende Einstellung für diesen Wert zu ermitteln.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Ändern der vorhandenen Webveröffentlichungsregel für die externe AutoErmittlungs-SAN und -URL

1. Öffnen Sie die Reverseproxyschnittstelle.
    
2. Sie müssen Ihre Webveröffentlichungsregel suchen und die Option "Bearbeiten" auswählen (je nach Konfiguration des Reverseproxys kann sie sich in einem Menü oder auf einer Registerkarte befinden).
    
3. Es sollte einen Bereich geben, der angibt, auf welche Webveröffentlichungsregel angewendet wird. Sie müssen diese Regel für eingehende Websites oder Anforderungen für Websites ändern. Sie fügen einen neuen Eintrag **hinzu.**
    
4. Geben Sie den Namen Ihrer AutoErmittlungswebsite ein (das Beispiel, das wir verwenden, ist lyncdiscover.contoso.com), und klicken Sie je nach Format des Reverseproxys auf **"OK"** oder **"Speichern".**
    
5. Möglicherweise verfügen Sie über ein neues Zertifikat mit dem AutoErmittlungs-SAN-Eintrag. Dies muss auch installiert und für die Verwendung gemäß den Einstellungen Ihres Reverseproxys konfiguriert werden. Achten Sie darauf, alles zu speichern, wenn die Konfiguration abgeschlossen ist.
    
6. Wenn Ihr Reverseproxy über eine **Testfunktion** verfügt, verwenden Sie diese, um sicherzustellen, dass alles ordnungsgemäß funktioniert.
    
7. Nun müssen Sie diese Schritte möglicherweise wiederholen, wenn Sie einen Director- oder Director-Pool in Ihrer Umgebung haben (dies bedeutet, dass Sie über eine zweite Regel verfügen).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Erstellen einer Webveröffentlichungsregel für die externe AutoErmittlungs-URL

1. Öffnen Sie die Reverseproxyschnittstelle.
    
2. Sie müssen auf der Benutzeroberfläche suchen, an der Sie Ihre Webveröffentlichungsregeln erstellen, und die Option **"Neu"** oder **"Erstellen"** auswählen (je nach Konfiguration des Reverseproxys kann es sich in einem Menü oder auf einer Registerkarte befinden). Sie suchen nach der Option zum Erstellen einer neuen Webveröffentlichungsregel.
    
3. In der Regel müssen Sie die folgenden Informationen eingeben:
    
   - **Name**: der Name für Die Regel
    
   - **Regelaktion:** In diesem Fall handelt es sich um eine **Allow-Regel,** sie lässt etwas über ihren Reverseproxy übergeben.
    
   - Die **Veröffentlichungsregel** oder -option, die Sie auswählen, ist **eine einzelne Website oder ein Lastenausgleich.**
    
   - Dies muss **SSL** für den externen Zugriff sein, wählen Sie diese Option aus.
    
   - Sie müssen einen Pfad für die **interne Veröffentlichung** veröffentlichen und den FQDN für die externen Webdienste im Lastenausgleichsmodul ihres Front-End-Pools eingeben (oder den FQDN des Lastenausgleichsmoduls des Directorpools, falls vorhanden). Ein Beispiel wäre sfb_pool01.contoso.local.
    
   - Sie sollten **/\\** _als den zu veröffentlichenden Pfad eingeben, aber Sie müssen auch _*den ursprünglichen Hostheader**weiterleiten.
    
   - Es gibt eine Option für details oder Informationen zu **öffentlichen oder externen Namen.** Hier können Sie Folgendes eingeben:
    
   - **Akzeptieren Sie Anforderungen,** aber es sollte sich um den Domänennamen handeln.
    
   - Geben Sie für den **Namen** **lyncdiscover ein.** <sipdomain> (Dies ist die externe AutoErmittlungsdienst-URL). Wenn Sie nun eine Regel für die URL für externe Webdienste im Front-End-Pool erstellen, müssen Sie den FQDN für die externen Webdienste im Front-End-Pool eingeben (z. B. lyncwebextpool01.contoso.com).
    
   - Es gibt eine **Pfadoption,** und Sie müssen **/\\** * hier eingeben.
    
   - Sie müssen einen **SSL-Listener** mit Ihrem aktuellen öffentlichen Zertifikat auswählen.
    
   - **Die Authentifizierungsdelegierung** sollte auf **"Keine Delegierung"** festgelegt werden, die direkte Clientauthentifizierung **sollte** jedoch zulässig sein.
    
   - Die Regel sollte auf **alle Benutzer** festgelegt werden.
    
   - Dies sollten alle Informationen sein, die Sie zum Erstellen dieser Regel benötigen, damit Sie fortfahren können.
    
4. Sie müssen sicherstellen, dass der **ursprüngliche Hostheader** weitergeleitet wird.
    
5. Die **Webserverports** müssen auch festgelegt werden. Sie müssen die folgenden Schritte ausführen:
    
   - **Umleitungsanforderungen an http-Port** und die Portnummer sollte **8080** sein.
    
   - **Umleitungsanforderungen an ssl-Port** und die Portnummer sollte **4443** sein.
    
6. Wenn alles konfiguriert ist, müssen Sie diese speichern oder anwenden, und dann sollten Sie die Regel testen.
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>Erstellen einer Webveröffentlichungsregel für Port 80 (optional)

1. Öffnen Sie die Reverseproxyschnittstelle.
    
2. Sie müssen auf der Benutzeroberfläche suchen, an der Sie Ihre Webveröffentlichungsregeln erstellen, und die Option **"Neu"** oder **"Erstellen"** auswählen (je nach Konfiguration des Reverseproxys kann es sich in einem Menü oder auf einer Registerkarte befinden). Sie suchen nach der Option zum Erstellen einer neuen Webveröffentlichungsregel.
    
3. In der Regel müssen Sie die folgenden Informationen eingeben:
    
   - **Name**: der Name für Die Regel
    
   - **Regelaktion:** In diesem Fall handelt es sich um eine **Allow-Regel,** sie lässt etwas über ihren Reverseproxy übergeben.
    
   - Die **Veröffentlichungsregel** oder -option, die Sie auswählen, ist **eine einzelne Website oder ein Lastenausgleich.**
    
   - Dies muss eine **nicht gesicherte Verbindung sein, um eine Verbindung mit dem veröffentlichten Webserver oder der veröffentlichten Farm herzustellen.**
    
   - Sie müssen einen Pfad für die **interne Veröffentlichung** veröffentlichen und den FQDN für die **VIP-Adresse** des Lastenausgleichsmoduls Ihres Front-End-Pools eingeben. Ein Beispiel wäre sfb_pool01.contoso.local.
    
   - Sie sollten **/\\** _als den zu veröffentlichenden Pfad eingeben, aber Sie müssen auch _*den ursprünglichen Hostheader**weiterleiten.
    
   - Es gibt eine Option für details oder Informationen zu **öffentlichen oder externen Namen.** Hier können Sie Folgendes eingeben:
    
   - **Akzeptieren Sie Anforderungen,** aber es sollte sich um den Domänennamen handeln.
    
   - Geben Sie für den **Namen** **lyncdiscover ein.** <sipdomain> (Dies ist die externe AutoErmittlungsdienst-URL).
    
   - Es gibt eine **Pfadoption,** und Sie müssen **/\\** * hier eingeben.
    
   - Sie müssen einen Weblistener auswählen oder zulassen, dass Ihr Reverseproxy einen für Sie erstellt.
    
   - **Die Authentifizierungsdelegierung** sollte auf **"Keine Delegierung"** festgelegt werden, die direkte Clientauthentifizierung sollte jedoch **nicht** zulässig sein.
    
   - Die Regel sollte auf **alle Benutzer** festgelegt werden.
    
   - Dies sollten alle Informationen sein, die Sie zum Erstellen dieser Regel benötigen, damit Sie fortfahren können.
    
4. Die **Webserverports** müssen festgelegt werden. Sie müssen folgendermaßen vorgehen:
    
   - **Umleitungsanforderungen an http-Port** und die Portnummer sollte **8080** sein.
    
   - **Umleitungsanforderungen an ssl-Port** und die Portnummer sollte **4443** sein.
    
5. Wenn alles konfiguriert ist, müssen Sie diese speichern oder anwenden, und dann sollten Sie die Regel testen.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Konfigurieren der AutoErmittlung für Mobilität mit Hybridbereitstellungen
<a name="ConfigAutoD"> </a>

Hybridumgebungen in Skype for Business Server sind Umgebungen, die eine lokale und eine O365-Umgebung kombinieren. Wenn Sie Skype for Business Server in einer Hybridumgebung arbeiten, muss der AutoErmittlungsdienst in der Lage sein, einen Benutzer aus einer dieser Umgebungen zu finden.
  
Damit mobile Clients ermitteln können, wo sich ein Benutzer befindet, muss der AutoErmittlungsdienst mit einem neuen URL (Uniform Resource Locator) konfiguriert werden. Das sind die Schritte:
  
1. Öffnen Sie Skype for Business Server Verwaltungsshell.
    
2. Führen Sie Folgendes aus, um den Wert des **Attributs ProxyFQDN** für Ihre Skype for Business Server Umgebung abzurufen:
    
   ```powershell
   Get-CsHostingProvider
   ```

3. Führen Sie dann im Shellfenster Folgendes aus:
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    Dabei wird [Identität] durch den Domänennamen des freigegebenen SIP-Adressraums ersetzt.
    
## <a name="test-your-mobility-deployment"></a>Testen der Mobilitätsbereitstellung
<a name="TestMobility"> </a>

Nachdem Sie Skype for Business Server Mobilitätsdienst und Skype for Business Server AutoErmittlungsdienst bereitgestellt haben, sollten Sie eine Testtransaktion ausführen, um sicherzustellen, dass Ihre Bereitstellung ordnungsgemäß funktioniert. Sie können **"Test-CsUcwaConference"** ausführen, um zu testen, wie zwei Benutzer eine Konferenz erstellen, daran teilnehmen und kommunizieren können. Sie benötigen zwei Benutzer (real oder test) und ihre vollständigen Anmeldeinformationen, um diese Tests durchzuführen. Dieser Befehl funktioniert sowohl für Skype for Business-Clients als auch für Lync Server 2013-Clients.
  
Für Lync Server 2010-Clients auf Skype for Business Server 2015 müssen Sie **Test-CsMcxP2PIM** zum Testen ausführen. Ihre Lync Server 2010-Benutzer müssen weiterhin tatsächliche Benutzer oder vordefinierte Testbenutzer sein, und Sie benötigen ihre Kennwortanmeldeinformationen.

> [!NOTE]
> McX(Mobility Service)-Unterstützung für mobile Legacyclients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen Skype for Business mobile Clients verwenden bereits unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Testen von Konferenzen für mobile Skype for Business- und Lync 2013-Clients

1. Melden Sie sich als Mitglied der **Rolle "CsAdministrator"** auf jedem Computer an, auf dem **Skype for Business Server Verwaltungsshell** und **Ocscore** installiert sind.
    
2. Starten Sie die **Skype for Business Server Verwaltungsshell** (Möglicherweise geben Sie den Namen in der Suche ein, oder wechseln Sie zu **"Alle Programme",** und wählen Sie ihn aus).
    
3. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   Es ist auch möglich, Anmeldeinformationen in einem Skript festzulegen und sie an das Test-Cmdlet zu übergeben. Nachfolgend finden Sie ein Beispiel dafür.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Testen von Konferenzen für mobile Lync 2010-Clients

> [!NOTE]
> McX(Mobility Service)-Unterstützung für mobile Legacyclients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen Skype for Business mobile Clients verwenden bereits unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.

1. Melden Sie sich als Mitglied der **Rolle "CsAdministrator"** auf jedem Computer an, auf dem **Skype for Business Server Verwaltungsshell** und **Ocscore** installiert sind.
    
2. Starten Sie die **Skype for Business Server Verwaltungsshell** (Möglicherweise geben Sie den Namen in der Suche ein, oder wechseln Sie zu **"Alle Programme",** und wählen Sie ihn aus).
    
3. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   Es ist auch möglich, Anmeldeinformationen in einem Skript festzulegen und sie an das Test-Cmdlet zu übergeben. Nachfolgend finden Sie ein Beispiel dafür.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

Weitere Informationen zu den Befehlsverfahren finden Sie unter ["Test-CsUcwaConference"](/powershell/module/skype/test-csucwaconference?view=skype-ps) und ["Test-CsMcxP2PIM".](/powershell/module/skype/test-csmcxp2pim?view=skype-ps)
  
## <a name="configure-for-push-notifications"></a>Konfigurieren von Pushbenachrichtigungen
<a name="ConfigPush"> </a>

Pushbenachrichtigungen in Form von Signalen, Symbolen oder Warnungen können auch dann an ein mobiles Gerät gesendet werden, wenn die Skype oder Lync-App inaktiv ist. Aber was sind Pushbenachrichtigungen? Es handelt sich um Ereignisbenachrichtigungen, z. B. eine neue oder verpasste Chateinladung oder für eine empfangene Voicemail. Der Skype for Business Server-Mobilitätsdienst sendet diese Benachrichtigungen an den cloudbasierten Skype for Business Server Pushbenachrichtigungsdienst, der dann die Benachrichtigungen für Windows Phone Benutzer an den Microsoft-Pushbenachrichtigungsdienst (Microsoft Push Notification Service, MSNS) sendet.
  
Diese Funktionalität ist seit Lync Server 2013 unverändert, aber wenn Sie über eine Skype for Business Server verfügen, sollten Sie folgendermaßen vorgehen:
  
- Fügen Sie für einen Skype for Business Server Edgeserver einen neuen Hostinganbieter, Microsoft Skype for Business Online, hinzu, und richten Sie dann einen Hostinganbieterverbund zwischen Ihrer Organisation und Skype for Business Online ein.
    
- Aktivieren Sie Pushbenachrichtigungen, indem Sie das Cmdlet **"Set-CsPushNotificationConfiguration"** ausführen. Pushbenachrichtigungen sind standardmäßig deaktiviert.
    
- Testen Sie die Verbundkonfiguration und Pushbenachrichtigungen.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Konfigurieren des Skype for Business-Edgeservers für Pushbenachrichtigungen

1. Melden Sie sich mit einem Konto, das Mitglied der **Rolle "CsAdministrator"** ist, auf einem Computer an, auf dem **Skype for Business Server Verwaltungsshell** und **Ocscore** installiert sind.
    
2. Starten Sie die **Skype for Business Server-Verwaltungsshell.**
    
3. Fügen Sie einen Skype for Business Server Onlinehostinganbieter hinzu.
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Beispiel:
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > Sie können nicht mehr als eine Verbundbeziehung mit einem einzigen Hostinganbieter haben. Wenn Sie also bereits einen Hostinganbieter eingerichtet haben, der über eine Verbundbeziehung mit sipfed.online.lync.com verfügt, fügen Sie keinen anderen Hostinganbieter hinzu, auch wenn die Identität des Hostinganbieters etwas anderes als SkypeOnline ist. 
  
4. Richten Sie den Hostinganbieterverbund zwischen Ihrer Organisation und dem Pushbenachrichtigungsdienst unter Skype for Business Online ein. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Aktivieren von Pushbenachrichtigungen

1. Melden Sie sich mit einem Konto, das Mitglied der **Rolle "CsAdministrator"** ist, auf einem Computer an, auf dem **Skype for Business Server Verwaltungsshell** und **Ocscore** installiert sind.
    
2. Starten Sie die **Skype for Business Server-Verwaltungsshell.**
    
3. Aktivieren Sie Pushbenachrichtigungen:
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Verbund aktivieren:
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>Testen von Partnerverbund- und Pushbenachrichtigungen

1. Melden Sie sich mit einem Konto, das Mitglied der **Rolle "CsAdministrator"** ist, auf einem Computer an, auf dem **Skype for Business Server Verwaltungsshell** und **Ocscore** installiert sind.
    
2. Starten Sie die **Skype for Business Server-Verwaltungsshell.**
    
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

Sie haben die Möglichkeit mit Skype for Business Server zu bestimmen, wer Ihren Mobilitätsdienst, Anruf über Arbeit, Voice over IP (VoIP) oder Video verwenden kann sowie ob WLAN für VoIP oder Video erforderlich ist. Mit "Über Arbeit anrufen" kann ein mobiler Benutzer beim Tätigen und Empfangen von Anrufen seine geschäftliche Telefonnummer anstelle seiner Mobiltelefonnummer verwenden. Die Person am anderen Ende der Leitung sieht die Mobiltelefonnummer dieses mobilen Benutzers nicht und ermöglicht es dem mobilen Benutzer, ausgehende Anrufgebühren zu vermeiden. Wenn VoIP und Video eingerichtet sind, können Benutzer VoIP-Anrufe und -Videos annehmen und tätigen. Die Einstellungen für die WLAN-Nutzung bestimmen, ob das mobile Gerät eines Benutzers für die Verwendung eines WLAN-Netzwerks über ein Mobilfunknetz erforderlich ist.
  
Mobilität, Anruf über Arbeit sowie die VoIP- und Videofunktionen sind standardmäßig aktiviert. Die Einstellung, für die WLAN für VoIP und Video erforderlich ist, ist deaktiviert. Ein Administrator hat die Möglichkeit, dies entweder global, nach Website oder nach Benutzer zu ändern.
  
Um Mobilitätsfeatures und "Anruf über Arbeit" verwenden zu können, müssen die Benutzer Folgendes sein:
  
- Aktiviert für Skype for Business Server
    
- Aktiviert für Enterprise-VoIP.
    
- Eine Mobilitätsrichtlinie zugewiesen, für die die **Option "EnableMobility"** auf **"True"** festgelegt ist.
    
Damit Benutzer "Anruf über Arbeit" verwenden können, müssen sie auch Folgendes tun:
  
- Eine VoIP-Richtlinie zugewiesen, für die die Option **"Gleichzeitiges Klingeln von Telefonen aktivieren"** ausgewählt ist.
    
- Eine Mobilitätsrichtlinie zugewiesen, deren **EnableOutsideVoice** auf **"True"** festgelegt ist.
    
> [!NOTE]
> Benutzer, die nicht für Enterprise-VoIP aktiviert sind, können ihre mobilen Geräte verwenden, um Skype zu Skype VoIP-Anrufen zu tätigen, oder sie können an Konferenzen teilnehmen, indem sie auf ihren mobilen Geräten auf den Link "Zum Beitreten klicken" klicken, wenn die entsprechenden Optionen für die VoIP-Richtlinie festgelegt sind, der sie zugeordnet sind. Weitere Details finden Sie im Planungsthema. 
  
### <a name="modify-global-mobility-policy"></a>Ändern der globalen Mobilitätsrichtlinie

1. Melden Sie sich mit einem Konto, das Mitglied der **Rolle "CsAdministrator"** ist, auf einem Computer an, auf dem **Skype for Business Server Verwaltungsshell** und **Ocscore** installiert sind.
    
2. Starten Sie die **Skype for Business Server-Verwaltungsshell.**
    
3. Deaktivieren Sie den Zugriff auf Mobilität und Anruf über Arbeit global, indem Sie Folgendes eingeben:
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Sie können "Anruf über Arbeit" deaktivieren, ohne den Zugriff auf Mobilität zu deaktivieren. Sie können die Mobilität jedoch nicht deaktivieren, ohne auch "Anruf über Arbeit" zu deaktivieren. 
  
    Weitere Informationen finden Sie unter ["Set-CsMobilityPolicy".](/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)
    
### <a name="modify-mobility-policy-by-site"></a>Ändern der Mobilitätsrichtlinie nach Standort

1. Melden Sie sich mit einem Konto, das Mitglied der **Rolle "CsAdministrator"** ist, auf einem Computer an, auf dem **Skype for Business Server Verwaltungsshell** und **Ocscore** installiert sind.
    
2. Starten Sie die **Skype for Business Server-Verwaltungsshell.**
    
3. Sie können eine Richtlinie auf Standortebene erstellen, VoIP und Video deaktivieren, WLAN für IP-Audio anfordern und WLAN für IP-Video nach Standort anfordern. Typ:
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Weitere Informationen finden Sie unter [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-user"></a>Ändern der Mobilitätsrichtlinie nach Benutzer

1. Melden Sie sich mit einem Konto, das Mitglied der **Rolle "CsAdministrator"** ist, auf einem Computer an, auf dem **Skype for Business Server Verwaltungsshell** und **Ocscore** installiert sind.
    
2. Starten Sie die **Skype for Business Server-Verwaltungsshell.**
    
3. Erstellen Sie Mobilitätsrichtlinien auf Benutzerebene, und deaktivieren Sie Mobilität und Anruf über Die Arbeit nach Benutzer. Typ:
    
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
