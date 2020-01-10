---
title: Bereitstellen und Konfigurieren von Mobility für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: In diesem Artikel werden die Schritte beschrieben, wie Sie eine vorhandene Skype for Business Server-Installation für die Nutzung des mobilitätsdiensts konfigurieren können, damit Ihre mobilen Geräte die Mobilitätsfunktionen von Skype for Business Server nutzen können.
ms.openlocfilehash: 3e39c354fd77d7ac36e3a4c36ed7e36e1d8ffbbf
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002865"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Bereitstellen und Konfigurieren von Mobility für Skype for Business Server  
 
In diesem Artikel werden die Schritte beschrieben, wie Sie eine vorhandene Skype for Business Server-Installation für die Nutzung des mobilitätsdiensts konfigurieren können, damit Ihre mobilen Geräte die Mobilitätsfunktionen von Skype for Business Server nutzen können.
  
Nachdem Sie den Artikel [Plan für Mobilität für Skype for Business Server](../plan-your-deployment/mobility.md) überprüft haben, sollten Sie mit den folgenden Schritten fortfahren, um die Mobilität in Ihrer Skype for Business Server-Umgebung bereitzustellen. Es handelt sich um folgende Schritte (in dieser Tabelle ist eine Liste der Berechtigungen enthalten):
  
|**Phase**|**Berechtigungen**|
|:-----|:-----|
|[Erstellen von DNS-Einträgen](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Domänen-Admins  <br/> DNSAdmins  <br/> |
|[Ändern von Zertifikaten](deploy-and-configure-mobility.md#ModCerts) <br/> |Lokaler Administrator  <br/> |
|[Konfigurieren des Reverseproxys](deploy-and-configure-mobility.md#ConfigRP) <br/> |Lokaler Administrator  <br/> |
|[Konfigurieren der AutoErmittlung für Mobilität mit Hybridbereitstellungen](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domänen-Admins  <br/> |
|[Testen der Mobilitätsbereitstellung](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[Konfigurieren von Pushbenachrichtigungen](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[Konfigurieren der Mobilitätsrichtlinie](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
Alle folgenden Abschnitte enthalten Schritte, bei denen davon ausgegangen wird, dass Sie das Planungsthema gelesen haben. Wenn Ihnen etwas unklar ist, können Sie dort nachlesen.

> [!NOTE]
> MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung. Alle derzeitigen mobilen Skype for Business-Clients verwenden bereits Unified Communications Web API (UCWA) zur Unterstützung von Instant Messaging (im), Anwesenheitsinformationen und Kontakten. Benutzer mit Legacy-Clients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
## <a name="create-dns-records"></a>Erstellen von DNS-Einträgen
<a name="CreateDNSRec"> </a>

Möglicherweise haben Sie diese bereits im Rahmen ihrer Skype for Business Server-Umgebung, aber Sie müssen die folgenden Einträge erstellen, damit AutoDiscovery funktioniert:
  
- Einen internen DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung über das Netzwerk Ihrer Organisation herstellen.
    
- Einen externen (bzw. öffentlichen) DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung von außerhalb des Netzwerks Ihrer Organisation herstellen.
    
Diese Einträge können entweder A(Host)-Namen oder CNAME-Einträge sein (es sind nicht beide erforderlich; hier werden lediglich die Schritte für alle Optionen erläutert).
  
### <a name="create-an-internal-dns-cname-record"></a>Erstellen eines internen DNS-CNAME-Eintrags

1. Melden Sie sich bei einem DNS-Server in Ihrem Netzwerk an, der entweder Mitglied der Gruppe **Domänen-Admins** oder der Gruppe **DnsAdmins** ist.
    
2. Klicken Sie auf **Start**, wählen Sie **Verwaltungstools** (möglicherweise müssen Sie **suchen**, da es sich nicht um eine Startmenüoption handelt), und klicken Sie dann auf **DNS**, um das DNS-Verwaltungs-Snap-In zu öffnen.
    
3. Im linken Bereich des Konsolenfensters müssen Sie zu der Domäne wechseln, die zu den Front-End-Servern Ihres Skype for Business-Servers gehört, und die **Forward-Lookupzonen** dort erweitern.
    
4. Prüfen Sie, welche der folgenden Einträge Sie haben:
    
   - Alle Host A-oder AAAA-Einträge für Ihren Front-End-Server (Standard oder Enterprise) oder Front-End-Pools (s).
    
   - Alle Host a-oder AAAA-Einträge für einen Director-oder Director-Pool (eine optionale Konfiguration, die Sie möglicherweise in Ihrer Bereitstellung haben).
    
5. Nachdem Sie dies festgestellt haben, klicken Sie mit der rechten Maustaste auf den SIP-Domänennamen und wählen Sie im Menü **Neuer Alias (CNAME)** aus.
    
6. Geben Sie im Textfeld **Aliasname** als Hostnamen für die URL des internen AutoErmittlungsdiensts „lyncdiscoverinternal“ ein.
    
7. Im **vollqualifizierten Domänennamen (FQDN für Ziel Host**) müssen Sie den internen Webdienst-FQDN für Ihren Front-End-Pool (oder einen einzelnen Front-End-Server oder Director-Pool oder Director) eingeben oder durchsuchen, der in Schritt 4 oben identifiziert wurde. Klicken Sie auf OK, wenn diese eingegeben wird.
    
8. Sie müssen einen neuen CNAME-Eintrag für die AutoErmittlung in der Forward-Nachschlage Zone für jede SIP-Domäne erstellen, die in Ihrer Skype for Business Server-Umgebung unterstützt wird.
    
### <a name="create-an-external-dns-cname-record"></a>Erstellen eines externen DNS-CNAME-Eintrags

1. Diese Schritte sind allgemein gehalten, da wir nicht wissen, welchen öffentlichen DNS-Anbieter Sie verwenden, Ihnen aber dennoch Hilfestellung leisten möchten. Melden Sie sich bei Ihrem öffentlichen DNS-Anbieter mit einem Konto an, über das neue DNS-Einträge vorgenommen werden können.
    
2. Zu diesem Zeitpunkt sollte bereits eine SIP-Domäne für Skype for Business Server vorhanden sein. Erweitern Sie die **Forward-Nachschlage Zone** für diese SIP-Domäne, oder öffnen Sie Sie auf andere Weise.
    
3. Prüfen Sie, welche der folgenden Einträge Sie haben:
    
   - Alle Host A-oder AAAA-Einträge für Ihren Front-End-Server (Standard oder Enterprise) oder Front-End-Pools (s).
    
   - Alle Host a-oder AAAA-Einträge für einen Director-oder Director-Pool (eine optionale Konfiguration, die Sie möglicherweise in Ihrer Bereitstellung haben).
    
4. Nachdem Sie diese Information haben, können Sie eine Option für die Erstellung von **Neuer Alias (CNAME)** auswählen.
    
5. Jetzt können Sie einen **Aliasnamen** eingeben. Geben Sie hier „lyndiscover“ für die externe AutoErmittlungsdienst-URL ein.
    
6. Als nächstes sollte ein Bereich vorhanden sein, der in einen **FQDN für den Ziel-Host**eingegeben werden muss, wobei es sich um den FQDN für Ihren Front-End-Pool (oder einen einzelnen Front-End-Server oder Director-Pool oder Director) handeln muss, der in Schritt 3 oben identifiziert wurde.
    
7. Möglicherweise müssen Sie hier speichern, oder wenn Sie zusätzliche CNAME-Einträge in der Forward-Lookupzone jeder SIP-Domäne in Ihrer Skype for Business Server-Umgebung erstellen müssen, sollten Sie dies tun, aber wenn Sie fertig sind, speichern Sie Ihre Arbeit.
    
### <a name="create-an-internal-dns-a-record"></a>Erstellen eines internen DNS-A-Eintrags

1. Melden Sie sich bei einem DNS-Server in Ihrem Netzwerk an, der entweder Mitglied der Gruppe **Domänen-Admins** oder der Gruppe **DnsAdmins** ist.
    
2. Klicken Sie auf **Start**, wählen Sie **Verwaltungstools** (möglicherweise müssen Sie **suchen**, da es sich nicht um eine Startmenüoption handelt), und klicken Sie dann auf **DNS**, um das DNS-Verwaltungs-Snap-In zu öffnen.
    
3. Im linken Bereich des Konsolenfensters müssen Sie zu der Domäne wechseln, die zu den Front-End-Servern Ihres Skype for Business-Servers gehört, und die **Forward-Lookupzonen** dort erweitern.
    
4. Prüfen Sie, welche der folgenden Einträge Sie haben:
    
   - Alle Host A-oder AAAA-Einträge für Ihren Front-End-Server (Standard oder Enterprise) oder Front-End-Pools (s).
    
   - Alle Host a-oder AAAA-Einträge für einen Director-oder Director-Pool (eine optionale Konfiguration, die Sie möglicherweise in Ihrer Bereitstellung haben).
    
5. Nachdem Sie dies festgestellt haben, klicken Sie mit der rechten Maustaste auf den SIP-Domänennamen und wählen Sie im Menü **Neuer Host (A oder AAAA)** aus.
    
6. Geben Sie im Textfeld **Name** als Hostnamen für die URL des internen AutoErmittlungsdiensts „lyncdiscoverinternal“ ein.
    
7. Geben Sie im Textfeld **IP-Adresse** die interne IP-Adresse des Webdiensts für Ihren Front-End-Pool (oder einen einzelnen Front-End-Server oder Director-Pool oder Director) ein, der in Schritt 4 oben identifiziert wurde.
    
8. Klicken Sie danach auf **Host hinzufügen** und dann auf **OK**.
    
9. Sie müssen eine neue Auto Ermittlungs-a-oder AAAA-Einträge in der Forward-Lookupzone für jede SIP-Domäne erstellen, die in Ihrer Skype for Business Server-Umgebung unterstützt wird. Wiederholen Sie hierfür die Schritte 6-8 so oft wie erforderlich.
    
10. Wenn Sie fertig sind, klicken Sie auf **Fertig**.
    
### <a name="create-an-external-dns-a-record"></a>Erstellen eines externen DNS-A-Eintrags

1. Diese Schritte sind allgemein gehalten, da wir nicht wissen, welchen öffentlichen DNS-Anbieter Sie verwenden, Ihnen aber dennoch Hilfestellung leisten möchten. Melden Sie sich bei Ihrem öffentlichen DNS-Anbieter mit einem Konto an, über das neue DNS-Einträge vorgenommen werden können.
    
2. Zu diesem Zeitpunkt sollte bereits eine SIP-Domäne für Skype for Business Server vorhanden sein. Erweitern Sie die **Forward-Nachschlage Zone** für diese SIP-Domäne, oder öffnen Sie Sie auf andere Weise.
    
3. Prüfen Sie, welche der folgenden Einträge Sie haben:
    
   - Alle Host A-oder AAAA-Einträge für Ihren Front-End-Server (Standard oder Enterprise) oder Front-End-Pools (s).
    
   - Alle Host a-oder AAAA-Einträge für einen Director-oder Director-Pool (eine optionale Konfiguration, die Sie möglicherweise in Ihrer Bereitstellung haben).
    
4. Nachdem Sie diese Information haben, können Sie eine Option für die Erstellung von **Neuer Host (A oder AAAA)** auswählen.
    
5. Jetzt können Sie einen **Namen** eingeben. Geben Sie hier „lyndiscover“ für die externe AutoErmittlungsdienst-URL ein.
    
6. Als nächstes sollte ein Bereich vorhanden sein, der in eine **IP-Adresse**eingegeben werden muss, wobei es sich um die IP-Adresse Ihres Front-End-Pools (oder eines einzelnen Front-End-Servers oder Director-Pools oder Directors) handeln muss, der in Schritt 3 oben identifiziert wurde.
    
7. Möglicherweise müssen Sie hier speichern, oder wenn Sie zusätzliche A-oder AAAA-Einträge in der Forward-Lookupzone jeder SIP-Domäne für Ihre Skype for Business Server-Umgebung erstellen müssen, sollten Sie dies tun, aber wenn Sie fertig sind, speichern Sie Ihre Arbeit.
    
## <a name="modify-certificates"></a>Ändern von Zertifikaten
<a name="ModCerts"> </a>

Wenn Sie Fragen zur Planung rund um Zertifikate haben, haben wir dies im Artikel [Planen der Mobilität für Skype for Business Server](../plan-your-deployment/mobility.md) dokumentiert. Nachdem Sie diese gelesen haben, werden Sie durch folgende Schritte geführt:
  
- Benötige ich neue Zertifikate?
    
- Anfordern neuer Zertifikate von der Zertifizierungsstelle.
    
- Aktualisieren der vorhandenen Zertifikate mit den Ersatzzertifikaten mithilfe der PowerShell.
    
- Überprüfen der Zertifikate mithilfe des Zertifikat-Snap-Ins in der Microsoft Management Console (MMC).
    
### <a name="do-i-need-new-certificates"></a>Benötige ich neue Zertifikate?

1. Zunächst müssen Sie möglicherweise überprüfen, welche Zertifikate direkt vorhanden sind und ob Sie über die erforderlichen Einträge verfügen. Dazu müssen Sie sich bei Ihrem Skype for Business-Server mit einem Konto anmelden, das ein lokaler Administrator ist. Dieses Konto muss möglicherweise auch über Rechte an der ausstellenden Zertifizierungsstelle (Certification Authority, ca) verfügen, für einige dieser Schritte.
    
2. Öffnen Sie die Skype for Business Server-Verwaltungsshell (Sie können die Suche verwenden, um Sie zu finden, wenn Sie Sie nicht an das Startmenü oder die Taskleiste angeheftet haben).
    
3. Sie müssen unbedingt wissen, welche Zertifikate Ihnen zugewiesen sind, bevor Sie versuchen, ein aktualisiertes Zertifikat hinzuzufügen. Geben Sie daher an der Befehlszeile Folgendes ein:
    
   ```powershell
   Get-CsCertificate
   ```

4. Die Informationen aus Schritt 3 sind für Sie eindeutig. Sie können Sie durchgehen, um festzustellen, ob Ihnen ein einzelnes Zertifikat für verschiedene Zwecke zugewiesen wurde, oder ob Sie über mehrere Zertifikate für die einzelnen Komponenten, die sie benötigen, verfügen. Über den Parameter **Verwendung** erfahren Sie, wie ein Zertifikat verwendet wird, und der Parameter **Fingerabdruck** gibt an, ob es sich um das gleiche Zertifikat oder mehrere Zertifikate handelt.
    
5. Wenn Sie über die in unserem Planungsabschnitt empfohlenen SAN-Einträge verfügen, ist alles in Ordnung. Falls nicht, müssen Sie ein neues Zertifikat bzw. mehrere Zertifikate (abhängig von Ihrer Konfiguration) bei der Zertifizierungsstelle beantragen.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>Anfordern eines neuen Zertifikats oder mehrerer Zertifikate von der Zertifizierungsstelle

1. Nachdem Sie geprüft haben, über welche SAN-Einträge Sie verfügen, wissen Sie, dass Sie ein **einzelnes Zertifikat** haben (nachdem Sie dies anhand der obigen Schritte geprüft haben), und dass Sie nicht über alle benötigten Einträge verfügen. Sie müssen bei Ihrer Zertifizierungsstelle ein neues Zertifikat beantragen. Öffnen Sie Ihre Skype for Business Server-PowerShell:
    
   - Für einen fehlenden AutoErmittlungsdienst-SAN (ersetzen Sie den Parameter -Ca durch den Pfad Ihrer Zertifizierungsstelle):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Wenn Sie nun über mehrere SIP-Domänen verfügen, können Sie den AllSipDomain-Parameter wie im obigen Beispiel nicht verwenden. Sie müssen stattdessen den Parameter „DomainName“ verwenden. Und wenn Sie den Parameter „DomainName“ verwenden, müssen Sie den vollqualifizierten Domänennamen für die Einträge „lyncdiscoverinternal“ und „lyncdiscover“ definieren. Ein Beispiel wäre Folgendes (ersetzen Sie den Parameter -Ca mit dem Pfad Ihrer Zertifizierungsstelle):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. Nachdem Sie geprüft haben, über welche SAN-Einträge Sie verfügen, wissen Sie, dass Sie **mehrere Zertifikate** haben und dass Sie nicht über alle benötigten Einträge verfügen. Sie müssen bei Ihrer Zertifizierungsstelle ein neues Zertifikat beantragen. Öffnen Sie Ihre Skype for Business Server-PowerShell:
    
   - Für einen fehlenden AutoErmittlungsdienst-SAN (ersetzen Sie den Parameter -Ca durch den Pfad Ihrer Zertifizierungsstelle):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Wenn Sie nun über mehrere SIP-Domänen verfügen, können Sie den AllSipDomain-Parameter wie im obigen Beispiel nicht verwenden. Sie müssen stattdessen den Parameter „DomainName“ verwenden. Und wenn Sie den Parameter „DomainName“ verwenden, müssen Sie den vollqualifizierten Domänennamen für die Einträge „lyncdiscoverinternal“ und „lyncdiscover“ definieren. Ein Beispiel wäre Folgendes (ersetzen Sie den Parameter -Ca mit dem Pfad Ihrer Zertifizierungsstelle):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - Nachdem die neuen Zertifikate von der Zertifizierungsstelle generiert wurden, müssen Sie sie zuweisen.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Zuweisen von Zertifikaten mit der Skype for Business Server-Verwaltungsshell

- Abhängig von den Ergebnissen im Abschnitt „Benötige ich neue Zertifikate“ oben müssen Sie **einen** der folgenden Befehle ausführen.
    
  - Wenn Sie ein einzelnes Zertifikat für alles haben (die Fingerabdrücke sind identisch), müssen Sie folgenden Befehl ausführen:
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - Wenn Sie verschiedene Zertifikate haben (die Fingerabdrücke sind unterschiedlich), führen Sie stattdessen folgenden Befehl aus:
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Anzeigen von Zertifikaten in der Microsoft Management Console (MMC)

1. Es gibt eine Option zum Anzeigen Ihrer Zertifikate mit dem Zertifikat-Snap-In für die MMC. Geben Sie einfach „MMC“ in das Suchfeld ein, und die Anwendungsoption wird angezeigt.
    
2. Um das Zertifikat-Snap-In hinzuzufügen, klicken Sie auf **Datei** und dann auf **Snap-In hinzufügen/entfernen...** (auch das Tastaturkürzel **Strg+M** kann verwendet werden). **Zertifikate** ist eine Option im linken Fensterbereich. Wählen Sie sie aus, und wählen Sie dann **Computerkonto** im Popup-Fenster. Klicken Sie dann auf **Weiter**.
    
3. Wenn Sie sich im Popupfenster befinden, ist es wahrscheinlich, dass Sie dies auf dem Computer machen, auf dem sich die Zertifikate befinden, die Sie sich ansehen müssen, daher sollten Sie die Auswahl auf dem **lokalen Computer** beibehalten, wenn das so ist. Wenn Sie an einem Remotecomputer arbeiten, ändern Sie das Optionsfeld auf **einen anderen Computer** , und geben Sie dann entweder den FQDN des Computers ein, oder verwenden Sie die Schaltfläche **Durchsuchen** , um nach diesem Computer über AD zu suchen. Nachdem Sie den Computer ausgewählt haben, müssen Sie auf Fertig **stellen** und dann auf **OK** klicken, um das Snap-in zur MMC hinzuzufügen.
    
4. Erweitern Sie den Abschnitt **Zertifikate** im linken Bereich der MMC. Erweitern Sie auch den **persönlichen Ordner**, und wählen Sie dann **Zertifikate** aus. Damit können Sie die Zertifikate in diesem Speicher anzeigen.
    
5. Sie müssen die anzuzeigenden Zertifikate suchen, mit der rechten Maustaste darauf klicken und die Option **Öffnen** wählen.
    
    > [!NOTE]
    > Woher wissen Sie, welches Zertifikat das ist? Es sollte entweder das einzelne Zertifikat sein, das allen für Ihre Farm zugewiesen ist, oder Sie haben möglicherweise mehrere Zertifikate für verschiedene Dinge, wie standardmäßige, interne Webdienste usw., in diesem Fall müssen Sie möglicherweise mehrere Zertifikate betrachten. Mehrere Zertifikate haben denselben Fingerabdruck. 
  
6. Nachdem Sie die **Zertifikat**-Ansicht geöffnet haben, wählen Sie **Details**. Dort sehen Sie den Zertifikatantragstellernamen, wenn Sie **Antragsteller** auswählen, und der zugewiesene Antragstellername und die zugeordneten Eigenschaften werden angezeigt.
    
7. Sie müssen auch die Einträge für den **alternativen Antragstellernamen** prüfen. Dort finden Sie einen oder mehrere der folgenden Einträge:
    
   - Der Poolname für diesen Pool oder der Name des einzelnen Servers, wenn es sich nicht um einen Pool handelt.
    
   - Den Namen des Servers, dem das Zertifikat zugewiesen wurde.
    
   - Einfache URL-Einträge, üblicherweise „meet“ und „dialin“.
    
   - Webdienste interne und Webdienste externe Namen (beispielsweise webpool01.contoso.net, webpool01.contoso.com), basierend auf den Optionen, die im Topologie-Generator und über berittenen Webdiensten ausgewählt wurden.
    
   - Wenn Sie bereits zugewiesen ist, wird die lyncdiscover. \<sipdomain\> und lyncdiscoverinternal. \<sipdomain\> -Datensätze.
    
     Wenn mehr als ein Zertifikat zugewiesen ist, müssen Sie mehrere Zertifikate prüfen (siehe Hinweis oben).
    
8. Wenn Sie also lyncdiscover finden. \<sipdomain\> und lyncdiscoverinternal. \<sipdomain\> Records, Sie haben diese bereits konfiguriert. Sie können die MMC schließen.
    
9. Wenn sie nicht zugewiesen sind, müssen Sie entweder ein neues Zertifikat beantragen stellen (wie oben beschrieben) oder die Zertifikate nach dem Antrag installieren (es wird empfohlen, hierfür wie oben beschrieben PowerShell zu verwenden).
    
## <a name="configure-the-reverse-proxy"></a>Konfigurieren des Reverseproxys
<a name="ConfigRP"> </a>

Die folgenden Schritte sind nicht zur exakten Befolgung gedacht. In früheren Produktversionen wurden Sie beispielsweise durch die Konfiguration von Threat Management Gateway (TMG) geführt, und wenn Sie dies nicht verwendeten, mussten Sie von dieser Stelle an Ihre eigene Version erarbeiten.
  
TMG wird von Microsoft nicht mehr als Produkt angeboten, und wenn Sie es noch konfigurieren müssen, können Sie sich die 2013-Schritte für [lync Server](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx)anschauen. Die folgenden Informationen sollten jedoch generell hilfreich sein, auch wenn es keine Möglichkeit gibt, spezielle Exemplarische Vorgehensweisen für jeden Reverse-Proxy bereitzustellen.
  
Es sind zwei Hauptpunkte zu berücksichtigen:
  
- Möchten Sie die anfängliche AutoErmittlung-Anforderung über HTTPS stellen (empfohlen)?
    
  - Wenn Sie über eine Webveröffentlichungsregel verfügen, müssen Sie diese ändern.
    
  - Wenn Sie noch nicht über eine Webveröffentlichungsregel verfügen, müssen Sie eine erstellen.
    
- Wenn Sie die anfängliche AutoErmittlung-Anforderung über HTTP stellen, müssen Sie diese Regel ebenfalls erstellen oder ändern.
    
> [!NOTE]
> **Wichtig** Ein Proxy-Timeoutwert ist eine Zahl, die von der Bereitstellung bis zur Bereitstellung variieren kann. Überwachen Sie Ihre Bereitstellung, und ändern Sie den Wert für die optimale Benutzerfreundlichkeit für Clients. Möglicherweise können Sie den Wert so einstellen, dass er so gering wie 200 ist. Wenn Sie lync Mobile-Clients in Ihrer Umgebung unterstützen, sollten Sie den Wert auf 960 setzen, um Timeouts für Push-Benachrichtigungen von Office 365 zu ermöglichen, die einen Timeoutwert von 900 aufweisen. Es ist sehr wahrscheinlich, dass Sie den Timeoutwert erhöhen müssen, um zu verhindern, dass der Client die Verbindung trennt, wenn der Wert zu klein ist, oder die Zahl verkleinern, wenn Verbindungen über den Proxy nicht getrennt, aber lange nach dem Trennen des Clients gelöscht werden. Das überwachen und Baselining, was für Ihre Umgebung üblich ist, ist die einzige genaue Möglichkeit, die entsprechende Einstellung für diesen Wert festzulegen.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Bearbeiten einer bestehenden Webveröffentlichungsregel für den externen AutoErmittlungsdienst-SAN und die -URL

1. Öffnen Sie die Reverse-Proxy-Schnittstelle.
    
2. Sie müssen die Webveröffentlichungsregel lokalisieren und die Option "Bearbeiten" auswählen (abhängig von der Konfiguration Ihres Reverse-Proxys).
    
3. Es sollte ein Bereich vorhanden sein, in dem angegeben ist, auf was diese Webveröffentlichungsregel angewendet wird. Sie müssen diese Regel für eingehende Websites oder Anforderungen für Websites ändern. Dafür müssen Sie einen neuen Eintrag **hinzufügen**.
    
4. Geben Sie den Namen der Auto Ermittlungs Website ein (das Beispiel, das wir verwenden werden, ist lyncdiscover.contoso.com), und klicken Sie je nach Format Ihres Reverse-Proxys auf **OK** oder **Speichern**.
    
5. Möglicherweise verfügen Sie über ein neues Zertifikat mit dem SAN-Eintrag für AutoErmittlung. Dieser muss ebenfalls installiert und für die Verwendung entsprechend den Einstellungen Ihres Reverse-Proxys konfiguriert sein. Vergessen Sie nicht, alles zu speichern, wenn die Konfiguration abgeschlossen ist.
    
6. Wenn Ihr Reverse-Proxy über eine **Test** Funktionalität verfügt, nutzen Sie ihn, um sicherzustellen, dass alles ordnungsgemäß funktioniert.
    
7. Möglicherweise müssen Sie diese Schritte nun wiederholen, wenn Sie einen Director-oder Director-Pool in Ihrer Umgebung haben (Dies würde bedeuten, dass Sie eine zweite Regel haben).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Erstellen einer Webveröffentlichungsregel für die externe Auto Ermittlungs-URL

1. Öffnen Sie die Reverse-Proxy-Schnittstelle.
    
2. Sie müssen ermitteln, wo Sie in der Benutzeroberfläche ihre Webveröffentlichungsregeln erstellen, und die Option **neu** oder **Erstellen** auswählen (je nach Konfiguration des Reverse-Proxys kann es sich um ein Menü oder eine Registerkarte handeln). Suchen Sie nach der Option zum Erstellen einer neuen Webveröffentlichungsregel.
    
3. In der Regel müssen Sie folgende Informationen eingeben:
    
   - **Name**: der Name Ihrer Regel
    
   - **Regelaktion**: in diesem Fall handelt es sich um eine **Zulassungs** Regel, bei der Sie etwas über Ihren Reverse-Proxy durchlaufen lassen.
    
   - Die Regel oder Option für die **Veröffentlichung**, die Sie auswählen, ist **einzelne Website oder Lastenausgleich**.
    
   - Für externen Zugriff muss es sich um **SSL** handeln; wählen Sie diese Option.
    
   - Sie müssen einen Pfad für die **interne Veröffentlichung**veröffentlichen und den FQDN für die externen Webdienste im Lastenausgleichsmodul des Front-End-Pools eingeben (oder den FQDN des Load Balancer des Director-Pools, wenn Sie einen haben), ein Beispiel wäre sfb_pool01. contoso. local.
    
   - Sie sollten * ** / **als den zu veröffentlichenden Pfad eingeben, Sie müssen aber auch **den ursprünglichen Hostheader weiterleiten**.
    
   - Sie finden eine Option für Details oder Informationen zum **öffentlichen oder externen Namen**. Dort können Sie Folgendes eingeben:
    
   - **Anforderungen akzeptieren**, dies sollte aber für den Domänennamen geschehen.
    
   - Geben Sie als **Namen** den Wert **lyncdiscover.** <sipdomain>(Dies ist die URL des externen AutoErmittlungsdiensts). Wenn Sie nun eine Regel für die externe Webdienste-URL im Front-End-Pool erstellen, müssen Sie den FQDN für die externen Webdienste in Ihrem Front-End-Pool eingeben (beispielsweise lyncwebextpool01.contoso.com).
    
   - Es wird eine **path** -Option geben, und Sie müssen * hier ** / **eingeben.
    
   - Wählen Sie mit Ihrem aktuellen öffentlichen Zertifikat einen **SSL-Listener** aus.
    
   - **Authentifizierungsdelegierung** muss auf **Keine Delegierung** festgelegt sein, aber direkte Clientauthentifizierung **muss** zulässig sein.
    
   - Diese Regel muss auf **Alle Benutzer** festgelegt werden.
    
   - Das dürften alle Informationen sein, die Sie zum Erstellen dieser Regel benötigen, damit Sie fortfahren können.
    
4. Sie müssen sicherstellen, dass der **ursprüngliche Hostheader** weitergeleitet wird.
    
5. Auch die **Webserver**-Ports müssen festgelegt werden. Gehen Sie wie folgt vor:
    
   - **Leiten Sie Anforderungen an den HTTP-Port weiter**. Die Portnummer muss **8080** lauten.
    
   - **Leiten Sie Anforderungen an den SSL-Port weiter**. Die Portnummer muss **4443** lauten.
    
6. Wenn alles konfiguriert ist, müssen Sie die Optionen speichern oder anwenden und sollten die Regel dann testen.
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>Erstellen einer Webveröffentlichungsregel für Port 80 (optional)

1. Öffnen Sie die Reverse-Proxy-Schnittstelle.
    
2. Sie müssen ermitteln, wo Sie in der Benutzeroberfläche ihre Webveröffentlichungsregeln erstellen, und die Option **neu** oder **Erstellen** auswählen (je nach Konfiguration des Reverse-Proxys kann es sich um ein Menü oder eine Registerkarte handeln). Suchen Sie nach der Option zum Erstellen einer neuen Webveröffentlichungsregel.
    
3. In der Regel müssen Sie folgende Informationen eingeben:
    
   - **Name**: der Name Ihrer Regel
    
   - **Regelaktion**: in diesem Fall handelt es sich um eine **Zulassungs** Regel, bei der Sie etwas über Ihren Reverse-Proxy durchlaufen lassen.
    
   - Die Regel oder Option für die **Veröffentlichung**, die Sie auswählen, ist **einzelne Website oder Lastenausgleich**.
    
   - Dabei muss es sich um eine **nicht gesicherte Verbindung zur Verbindung mit dem veröffentlichten Webserver bzw. der Farm handeln**.
    
   - Sie müssen einen Pfad für die **interne Veröffentlichung**veröffentlichen, und geben Sie den FQDN für die VIP- **Adresse** des Load Balancer des Front-End-Pools ein, beispielsweise sfb_pool01. contoso. local.
    
   - Sie sollten * ** / **als den zu veröffentlichenden Pfad eingeben, Sie müssen aber auch **den ursprünglichen Hostheader weiterleiten**.
    
   - Sie finden eine Option für Details oder Informationen zum **öffentlichen oder externen Namen**. Dort können Sie Folgendes eingeben:
    
   - **Anforderungen akzeptieren**, dies sollte aber für den Domänennamen geschehen.
    
   - Geben Sie als **Namen** den Wert **lyncdiscover.** <sipdomain>(Dies ist die URL des externen AutoErmittlungsdiensts).
    
   - Es wird eine **path** -Option geben, und Sie müssen * hier ** / **eingeben.
    
   - Sie müssen einen Weblistener auswählen oder zulassen, dass der Reverse-Proxy eine für Sie erstellt.
    
   - **Authentifizierungsdelegierung** muss auf **Keine Delegierung** festgelegt sein, aber direkte Clientauthentifizierung **darf nicht** zulässig sein.
    
   - Diese Regel muss auf **Alle Benutzer** festgelegt werden.
    
   - Das dürften alle Informationen sein, die Sie zum Erstellen dieser Regel benötigen, damit Sie fortfahren können.
    
4. Die **Webserver**-Ports müssen festgelegt werden. Gehen Sie wie folgt vor:
    
   - **Leiten Sie Anforderungen an den HTTP-Port weiter**. Die Portnummer muss **8080** lauten.
    
   - **Leiten Sie Anforderungen an den SSL-Port weiter**. Die Portnummer muss **4443** lauten.
    
5. Wenn alles konfiguriert ist, müssen Sie die Optionen speichern oder anwenden und sollten die Regel dann testen.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Konfigurieren der AutoErmittlung für Mobilität mit Hybridbereitstellungen
<a name="ConfigAutoD"> </a>

Hybrid Umgebungen in Skype for Business Server sind Umgebungen, in denen eine lokale und Office 365 Umgebung kombiniert werden. Wenn Sie Skype for Business Server in einer Hybrid Umgebung verwenden, muss der AutoErmittlungsdienst in der Lage sein, einen Benutzer aus einer dieser Umgebungen zu finden.
  
Damit Mobilclients ermitteln können, wo sich ein Benutzer befindet, muss der AutoErmittlungsdienst mit einem neuen Uniform Resource Locator (URL) konfiguriert sein. Führen Sie folgende Schritte aus:
  
1. Öffnen Sie die Skype for Business Server-Verwaltungsshell.
    
2. Führen Sie die folgenden Schritte aus, um den Wert des Attributs **ProxyFQDN** für Ihre Skype for Business Server-Umgebung zu erhalten:
    
   ```powershell
   Get-CsHostingProvider
   ```

3. Führen Sie dann im Shellfenster folgenden Befehl aus:
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    Hierbei wird [identity] durch den Domänennamen des freigegebenhen SIP-Adressraums ersetzt.
    
## <a name="test-your-mobility-deployment"></a>Testen der Mobilitätsbereitstellung
<a name="TestMobility"> </a>

Nachdem Sie Skype for Business Server Mobility Service und den AutoErmittlungsdienst für Skype for Business Server bereitgestellt haben, sollten Sie eine Testtransaktion ausführen, um sicherzustellen, dass die Bereitstellung richtig funktioniert. Sie können **Test-CsUcwaConference** ausführen, um die Fähigkeit zweier Benutzer zu testen, eine Konferenz zu erstellen, daran teilzunehmen und darin zu kommunizieren. Sie benötigen zwei Benutzer (echte oder Testbenutzer) und deren vollständige Anmeldeinformationen für diesen Test. Dieser Befehl funktioniert sowohl für Skype for Business-Clients als auch für lync Server 2013-Clients.
  
Für lync Server 2010-Clients in Skype for Business Server 2015 müssen Sie **Test-CsMcxP2PIM** ausführen, um zu testen. Ihre lync Server 2010-Benutzer müssen weiterhin tatsächliche Benutzer oder vordefinierte Testbenutzer sein, und Sie benötigen Ihre Kennwort-Anmeldeinformationen.

> [!NOTE]
> MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung. Alle derzeitigen mobilen Skype for Business-Clients verwenden bereits Unified Communications Web API (UCWA) zur Unterstützung von Instant Messaging (im), Anwesenheitsinformationen und Kontakten. Benutzer mit Legacy-Clients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Testkonferenz für Skype for Business- und Lync 2013-Mobilclients

1. Melden Sie sich als Mitglied der **CsAdministrator** -Rolle auf jedem Computer an, auf dem die **Skype for Business Server-Verwaltungsshell** und **OCSCore** installiert sind.
    
2. Starten Sie die **Skype for Business Server-Verwaltungsshell** (geben Sie möglicherweise den Namen in suchen ein, oder wechseln Sie zu **Alle Programme** , und wählen Sie ihn aus) aus.
    
3. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   Sie können auch Anmeldeinformationen in einem Skript festlegen und sie an das Test-Cmdlet übergeben. Dafür sehen Sie unten ein Beispiel.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Konferenztest für Lync 2010-Mobilclients

> [!NOTE]
> MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung. Alle derzeitigen mobilen Skype for Business-Clients verwenden bereits Unified Communications Web API (UCWA) zur Unterstützung von Instant Messaging (im), Anwesenheitsinformationen und Kontakten. Benutzer mit Legacy-Clients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.

1. Melden Sie sich als Mitglied der **CsAdministrator** -Rolle auf jedem Computer an, auf dem die **Skype for Business Server-Verwaltungsshell** und **OCSCore** installiert sind.
    
2. Starten Sie die **Skype for Business Server-Verwaltungsshell** (geben Sie möglicherweise den Namen in suchen ein, oder wechseln Sie zu **Alle Programme** , und wählen Sie ihn aus) aus.
    
3. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   Sie können auch Anmeldeinformationen in einem Skript festlegen und sie an das Test-Cmdlet übergeben. Dafür sehen Sie unten ein Beispiel.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

Weitere Informationen zu den Befehlsverfahren finden Sie unter [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) und [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).
  
## <a name="configure-for-push-notifications"></a>Konfigurieren von Pushbenachrichtigungen
<a name="ConfigPush"> </a>

Pushbenachrichtigungen in Form von Badges, Symbolen oder Warnungen können an ein Mobilgerät gesendet werden, selbst wenn die Skype- oder Lync-App inaktiv ist. Was sind aber Push-Benachrichtigungen? Dabei handelt es sich um Ereignisbenachrichtigungen, wie neue oder verpasste Chateinladungen oder eine erhaltene Voicemail. Der Skype for Business Server-Mobilitätsdienst sendet diese Benachrichtigungen an den Cloud-basierten Push-Benachrichtigungsdienst von Skype for Business Server, der dann die Benachrichtigungen an den Microsoft Push Notification Service (MSNs) für Windows Phone-Benutzer sendet.
  
Diese Funktionalität ist in lync Server 2013 unverändert, doch wenn Sie über einen Skype for Business-Server verfügen, sollten Sie die folgenden Schritte ausführen:
  
- Bei einem Skype for Business Server-Edgeserver fügen Sie einen neuen Hostinganbieter, Microsoft Skype for Business Online, und dann den Anbieter für den Hostinganbieter zwischen Ihrer Organisation und Skype for Business Online ein.
    
- Aktivieren Sie Pushbenachrichtigungen, indem Sie das Cmdlet **Set-CsPushNotificationConfiguration** ausführen. Pushbenachrichtigungen sind standardmäßig deaktiviert.
    
- Testen Sie die Partnerverbundkonfiguration und die Pushbenachrichtigungen.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Konfigurieren des Skype for Business Edge Server für Pushbenachrichtigungen

1. Melden Sie sich mit einem Konto an, das ein Mitglied der **CsAdministrator** -Rolle ist, auf einem Computer, auf dem die **Skype for Business Server-Verwaltungsshell** und **OCSCore** installiert sind.
    
2. Starten Sie die **Skype for Business Server-Verwaltungsshell**.
    
3. Fügen Sie einen Skype for Business Server Online-Hostinganbieter hinzu.
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Beispiel:
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > Es kann nur maximal eine Partnerverbundbeziehung mit einem einzelnen Hostinganbieter bestehen. Wenn Sie also bereits einen Hostinganbieter eingerichtet haben, der eine Partnerverbundbeziehung mit „sipfed.online.lync.com“ hat, fügen Sie keinen weiteren Hostinganbieter hinzu, auch wenn die Identität des Hostinganbieters nicht „LyncOnline“ ist. 
  
4. Richten Sie den Anbieter Verband für den Hostinganbieter zwischen Ihrer Organisation und dem Push-Benachrichtigungsdienst in Skype for Business Online ein. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Aktivieren von Pushbenachrichtigungen

1. Melden Sie sich mit einem Konto an, das ein Mitglied der **CsAdministrator** -Rolle ist, auf einem Computer, auf dem die **Skype for Business Server-Verwaltungsshell** und **OCSCore** installiert sind.
    
2. Starten Sie die **Skype for Business Server-Verwaltungsshell**.
    
3. Aktivieren Sie Pushbenachrichtigungen:
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Aktivieren Sie den Partnerverbund:
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>des Partnerverbunds und der Pushbenachrichtigungen

1. Melden Sie sich mit einem Konto an, das ein Mitglied der **CsAdministrator** -Rolle ist, auf einem Computer, auf dem die **Skype for Business Server-Verwaltungsshell** und **OCSCore** installiert sind.
    
2. Starten Sie die **Skype for Business Server-Verwaltungsshell**.
    
3. Testen Sie die Partnerverbundkonfiguration:
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    Beispiel:
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. Testen Sie die Pushbenachrichtigungen:
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    Beispiel:
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>Konfigurieren der Mobilitätsrichtlinie
<a name="ConfigMob"> </a>

Sie haben die Möglichkeit, mit Skype for Business Server festzustellen, wer Ihren Mobilitätsdienst nutzen, über Arbeit anrufen, VoIP (Voice over IP) oder Video verwenden oder ob WLAN für VoIP oder Video erforderlich ist. Mit der Funktion „Geschäftlich anrufen“ kann ein Benutzer Anrufe auf seinem Mobiltelefon unter Verwendung seiner geschäftlichen Telefonnummer anstatt seiner Mobilfunknummer tätigen und entgegennehmen. Der Gesprächspartner kann die Mobiltelefonnummer dieses Mobilbenutzers nicht sehen, und der Mobilbenutzer kann damit ausgehende Anrufgebühren vermeiden. Wenn VoIP und Video eingerichtet sind, können Benutzer VoIP-Anrufe annehmen und tätigen und Video nutzen. Mit den Einstellungen für WLAN-Nutzung wird festgelegt, ob das Mobilgerät eines Benutzers ein WLAN-Netzwerk über ein mobiles Datennetzwerk nutzen muss.
  
Mobilität, Anruf über die Arbeit und die VoIP-und Videofunktionen sind standardmäßig aktiviert. Die Einstellungen, die WLAN für VoIP und Video erfordern, sind deaktiviert. Administratoren können dies entweder global, nach Standort oder nach Benutzer ändern.
  
Um Mobilitätsfunktionen nutzen und über die Arbeit anrufen zu können, müssen die Benutzer:
  
- Für Skype for Business Server aktiviert
    
- Aktiviert für Enterprise-VoIP
    
- Eine Mobilitätsrichtlinie zugewiesen, bei der die Option **EnableMobility** auf " **true**" festgelegt ist.
    
Damit Benutzer die Funktion „Geschäftlich anrufen“ verwenden können, muss auf sie zudem Folgendes zutreffen:
  
- Ihnen muss eine VoIP-Richtlinie zugewiesen sein, für die die Option **Gleichzeitiges Klingeln von Telefonen aktivieren** aktiviert ist.
    
- Hat eine Mobilitätsrichtlinie zugewiesen, bei der die **EnableOutsideVoice** auf " **true**" festgelegt ist.
    
> [!NOTE]
> Benutzer, die nicht für Enterprise-VoIP aktiviert sind, können mithilfe ihrer Mobilgeräte VoIP-Anrufe zwischen Skype-Benutzern tätigen oder an Konferenzen teilnehmen, indem sie auf ihrem mobilen Gerät den Link „Zum Beitreten klicken“ nutzen. Hierzu müssen die entsprechenden Optionen für die VoIP-Richtlinie, der sie zugeordnet sind, festgelegt sein. Weitere Informationen finden Sie im Planungsthema. 
  
### <a name="modify-global-mobility-policy"></a>Ändern der globalen Mobilitätsrichtlinie

1. Melden Sie sich mit einem Konto an, das ein Mitglied der **CsAdministrator** -Rolle ist, auf einem Computer, auf dem die **Skype for Business Server-Verwaltungsshell** und **OCSCore** installiert sind.
    
2. Starten Sie die **Skype for Business Server-Verwaltungsshell**.
    
3. Deaktivieren Sie den Zugriff auf Mobilität, und rufen Sie über Work Global an, indem Sie Folgendes eingeben:
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Sie können den Anruf über die Arbeit ausschalten, ohne den Zugriff auf Mobilität zu deaktivieren. Sie können die Mobilität aber nicht deaktivieren, ohne den Anruf über die Arbeit abzuschalten. 
  
    Weitere Informationen finden Sie unter [Satz-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-site"></a>Ändern der mobilitätsrichtlinien nach Website

1. Melden Sie sich mit einem Konto an, das ein Mitglied der **CsAdministrator** -Rolle ist, auf einem Computer, auf dem die **Skype for Business Server-Verwaltungsshell** und **OCSCore** installiert sind.
    
2. Starten Sie die **Skype for Business Server-Verwaltungsshell**.
    
3. Sie können eine Richtlinie auf Standortebene erstellen, den Zugriff auf VoIP und Video deaktivieren und je nach Standort die Einstellungen aktivieren, die WLAN für IP-Audio und -Video erfordern. Geben Sie Folgendes ein:
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Weitere Informationen finden Sie unter [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-user"></a>Ändern der mobilitätsrichtlinien nach Benutzer

1. Melden Sie sich mit einem Konto an, das ein Mitglied der **CsAdministrator** -Rolle ist, auf einem Computer, auf dem die **Skype for Business Server-Verwaltungsshell** und **OCSCore** installiert sind.
    
2. Starten Sie die **Skype for Business Server-Verwaltungsshell**.
    
3. Erstellen Sie mobilitätsrichtlinien auf Benutzerebene, deaktivieren Sie Mobilität, und rufen Sie Sie über die Arbeit des Benutzers an. Geben Sie Folgendes ein:
    
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
    > Sie können den Anruf über die Arbeit ausschalten, ohne den Zugriff auf Mobilität zu deaktivieren. Sie können die Mobilität aber nicht deaktivieren, ohne den Anruf über die Arbeit abzuschalten. 
  

