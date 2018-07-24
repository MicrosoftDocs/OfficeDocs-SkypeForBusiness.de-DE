---
title: Bereitstellen und Konfigurieren von Mobilität für Skype Business Server
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Dieser Artikel führt Sie durch die Schritte zum Konfigurieren einer vorhandenen Skype für Business Server-Installation zum Verwenden des mobilitätsdienst, sodass Ihre mobilen Geräte Skype für Business Server Mobilitätsfeatures nutzen können.
ms.openlocfilehash: c8d30f11fed3b6c45f06b7e21f0038bee0274df4
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003138"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Bereitstellen und Konfigurieren von Mobilität für Skype Business Server  
 
Dieser Artikel führt Sie durch die Schritte zum Konfigurieren einer vorhandenen Skype für Business Server-Installation zum Verwenden des mobilitätsdienst, sodass Ihre mobilen Geräte Skype für Business Server Mobilitätsfeatures nutzen können.
  
Müssen überprüft den Artikel [für die Mobilität für Skype für Business Server planen](../plan-your-deployment/mobility.md) , sollten Sie die unten beschriebenen Schritte zum Bereitstellen von Mobilität in Ihrer Skype für Business Server-Umgebung fortsetzen bereit sein. Es handelt sich um folgende Schritte (in dieser Tabelle ist eine Liste der Berechtigungen enthalten):
  
|**Phase**|**Berechtigungen**|
|:-----|:-----|
|[Erstellen von DNS-Einträgen](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Domänen-Admins  <br/> DNSAdmins  <br/> |
|[Ändern von Zertifikaten](deploy-and-configure-mobility.md#ModCerts) <br/> |Lokaler Administrator  <br/> |
|[Konfigurieren des Reverseproxys](deploy-and-configure-mobility.md#ConfigRP) <br/> |Lokaler Administrator  <br/> |
|[Konfigurieren der AutoErmittlung für Mobilität mit Hybridbereitstellungen](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domänen-Admins  <br/> |
|[Testen der Mobilitätsbereitstellung](deploy-and-configure-mobility.md#TestMobility) <br/> |"Csadministrator"  <br/> |
|[Konfigurieren von Pushbenachrichtigungen](deploy-and-configure-mobility.md#ConfigPush) <br/> |"RTCUniversalServerAdmins"  <br/> |
|[Konfigurieren der Mobilitätsrichtlinie](deploy-and-configure-mobility.md#ConfigMob) <br/> |"Csadministrator"  <br/> |
   
Alle folgenden Abschnitte enthalten Schritte, bei denen davon ausgegangen wird, dass Sie das Planungsthema gelesen haben. Wenn Ihnen etwas unklar ist, können Sie dort nachlesen.

> [!NOTE]
> MCX-Unterstützung für mobile Clients von Vorversionen ist nicht mehr in Skype für Business Server 2019 verfügbar. Die Benutzer müssen an einen aktuellen Client aktualisieren.
  
## <a name="create-dns-records"></a>Erstellen von DNS-Einträgen
<a name="CreateDNSRec"> </a>

Möglicherweise verfügen Sie bereits diese als Teil Ihrer Skype für Business Server-Umgebung, aber Sie müssen die folgenden Einträge für die AutoErmittlung zu erstellen:
  
- Einen internen DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung über das Netzwerk Ihrer Organisation herstellen.
    
- Einen externen (bzw. öffentlichen) DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung von außerhalb des Netzwerks Ihrer Organisation herstellen.
    
Diese Einträge können entweder A(Host)-Namen oder CNAME-Einträge sein (es sind nicht beide erforderlich; hier werden lediglich die Schritte für alle Optionen erläutert).
  
### <a name="create-an-internal-dns-cname-record"></a>Erstellen eines internen DNS-CNAME-Eintrags

1. Melden Sie sich bei einem DNS-Server in Ihrem Netzwerk an, der entweder Mitglied der Gruppe **Domänen-Admins** oder der Gruppe **DnsAdmins** ist.
    
2. Klicken Sie auf **Start**, wählen Sie **Verwaltungstools** (möglicherweise müssen Sie **suchen**, da es sich nicht um eine Startmenüoption handelt), und klicken Sie dann auf **DNS**, um das DNS-Verwaltungs-Snap-In zu öffnen.
    
3. Im linken Bereich des Konsolenfenster, benötigen Sie fahren Sie mit der Domäne, der Startseite auf Ihre Skype für Business Server Front-End-Server, und erweitern Sie die **Forward-Lookupzonen** vorhanden.
    
4. Prüfen Sie, welche der folgenden Einträge Sie haben:
    
   - Alle Host A oder AAAA-Einträge für den Front-End-Server (Standard oder Enterprise) oder Front-End-Pools.
    
   - Jeder Host-A oder AAAA-Einträge für einen Director oder Director-pool (eine optionale Konfiguration, die Sie in Ihrer Bereitstellung möglicherweise).
    
5. Nachdem Sie dies festgestellt haben, klicken Sie mit der rechten Maustaste auf den SIP-Domänennamen und wählen Sie im Menü **Neuer Alias (CNAME)** aus.
    
6. Geben Sie im Textfeld **Aliasname** als Hostnamen für die URL des internen AutoErmittlungsdiensts „lyncdiscoverinternal“ ein.
    
7. In der **vollqualifizierten Domänennamen (FQDN für den Zielhost**, müssen Sie geben, oder wechseln Sie zu den internen Webdienste-FQDN für Ihre Front-End-Pool (oder einzelnen Front-End-Server oder Director-Pool oder Director) identifiziert, die in Schritt 4. Klicken Sie auf OK, wenn dies eingegeben wurde.
    
8. Sie müssen zum Erstellen eines neuen Autodiscover CNAME-Eintrags in der forward-Lookupzone für jede SIP-Domäne in Ihrer Skype für Business Server-Umgebung unterstützt.
    
### <a name="create-an-external-dns-cname-record"></a>Erstellen eines externen DNS-CNAME-Eintrags

1. Diese Schritte sind allgemein gehalten, da wir nicht wissen, welchen öffentlichen DNS-Anbieter Sie verwenden, Ihnen aber dennoch Hilfestellung leisten möchten. Melden Sie sich bei Ihrem öffentlichen DNS-Anbieter mit einem Konto an, über das neue DNS-Einträge vorgenommen werden können.
    
2. Zu diesem Zeitpunkt sollte eine SIP-Domäne bereits vorhanden Skype für Business Server vorhanden ist. Erweitern Sie die **Forward-Lookupzone** für diese SIP-Domäne, oder öffnen Sie sie andernfalls einrichten.
    
3. Prüfen Sie, welche der folgenden Einträge Sie haben:
    
   - Alle Host A oder AAAA-Einträge für den Front-End-Server (Standard oder Enterprise) oder Front-End-Pools.
    
   - Jeder Host-A oder AAAA-Einträge für einen Director oder Director-pool (eine optionale Konfiguration, die Sie in Ihrer Bereitstellung möglicherweise).
    
4. Nachdem Sie diese Information haben, können Sie eine Option für die Erstellung von **Neuer Alias (CNAME)** auswählen.
    
5. Jetzt können Sie einen **Aliasnamen** eingeben. Geben Sie hier „lyndiscover“ für die externe AutoErmittlungsdienst-URL ein.
    
6. Als Nächstes sollte ein Bereich in einem **FQDN für den Zielhost**eingeben, dies muss der FQDN für Ihre Front-End-Pool (oder einzelnen Front-End-Server oder Director-Pool oder Director) oben in Schritt 3 identifiziert werden.
    
7. Möglicherweise müssen Sie hier speichern, oder wenn Sie zusätzliche CNAME-Einträge in der forward-Lookupzone jeder SIP-Domäne in Ihrer Skype für Business Server-Umgebung erstellen müssen, sollten Sie tun, aber Freigabemodus bereit, speichern Sie Ihre Arbeit.
    
### <a name="create-an-internal-dns-a-record"></a>Erstellen eines internen DNS-A-Eintrags

1. Melden Sie sich bei einem DNS-Server in Ihrem Netzwerk an, der entweder Mitglied der Gruppe **Domänen-Admins** oder der Gruppe **DnsAdmins** ist.
    
2. Klicken Sie auf **Start**, wählen Sie **Verwaltungstools** (möglicherweise müssen Sie **suchen**, da es sich nicht um eine Startmenüoption handelt), und klicken Sie dann auf **DNS**, um das DNS-Verwaltungs-Snap-In zu öffnen.
    
3. Im linken Bereich des Konsolenfenster, benötigen Sie fahren Sie mit der Domäne, der Startseite auf Ihre Skype für Business Server Front-End-Server, und erweitern Sie die **Forward-Lookupzonen** vorhanden.
    
4. Prüfen Sie, welche der folgenden Einträge Sie haben:
    
   - Alle Host A oder AAAA-Einträge für den Front-End-Server (Standard oder Enterprise) oder Front-End-Pools.
    
   - Jeder Host-A oder AAAA-Einträge für einen Director oder Director-pool (eine optionale Konfiguration, die Sie in Ihrer Bereitstellung möglicherweise).
    
5. Nachdem Sie dies festgestellt haben, klicken Sie mit der rechten Maustaste auf den SIP-Domänennamen und wählen Sie im Menü **Neuer Host (A oder AAAA)** aus.
    
6. Geben Sie im Textfeld **Name** als Hostnamen für die URL des internen AutoErmittlungsdiensts „lyncdiscoverinternal“ ein.
    
7. Im Textfeld **IP-Adresse** identifiziert Typ die interne Webdienste-IP-Adresse für Ihre Front-End-Pool (oder einzelnen Front-End-Server oder Director-Pool oder Director) oben in Schritt 4.
    
8. Klicken Sie danach auf **Host hinzufügen** und dann auf **OK**.
    
9. Sie müssen zum Erstellen einer neuen Autodiscover A oder AAAA-Einträge in der forward-Lookupzone für jede SIP-Domäne in Ihrer Skype für Business Server-Umgebung unterstützt. Wiederholen Sie hierfür die Schritte 6-8 so oft wie erforderlich.
    
10. Wenn Sie fertig sind, klicken Sie auf **Fertig**.
    
### <a name="create-an-external-dns-a-record"></a>Erstellen eines externen DNS-A-Eintrags

1. Diese Schritte sind allgemein gehalten, da wir nicht wissen, welchen öffentlichen DNS-Anbieter Sie verwenden, Ihnen aber dennoch Hilfestellung leisten möchten. Melden Sie sich bei Ihrem öffentlichen DNS-Anbieter mit einem Konto an, über das neue DNS-Einträge vorgenommen werden können.
    
2. Zu diesem Zeitpunkt sollte eine SIP-Domäne bereits vorhanden Skype für Business Server vorhanden ist. Erweitern Sie die **Forward-Lookupzone** für diese SIP-Domäne, oder öffnen Sie sie andernfalls einrichten.
    
3. Prüfen Sie, welche der folgenden Einträge Sie haben:
    
   - Alle Host A oder AAAA-Einträge für den Front-End-Server (Standard oder Enterprise) oder Front-End-Pools.
    
   - Jeder Host-A oder AAAA-Einträge für einen Director oder Director-pool (eine optionale Konfiguration, die Sie in Ihrer Bereitstellung möglicherweise).
    
4. Nachdem Sie diese Information haben, können Sie eine Option für die Erstellung von **Neuer Host (A oder AAAA)** auswählen.
    
5. Jetzt können Sie einen **Namen** eingeben. Geben Sie hier „lyndiscover“ für die externe AutoErmittlungsdienst-URL ein.
    
6. Als Nächstes sollte ein Bereich in einer **IP-Adresse**eingeben, dies muss die IP-Adresse für Ihre Front-End-Pool (oder einzelnen Front-End-Server oder Director-Pool oder Director) oben in Schritt 3 identifiziert werden.
    
7. Möglicherweise müssen Sie hier speichern, oder wenn Sie zusätzliche erstellen müssen A oder AAAA-Einträge in der forward-Lookupzone jeder SIP-Domäne für Ihre Skype für Business Server-Umgebung, sollte, aber einmal können Sie jetzt, speichern Sie Ihre Arbeit.
    
## <a name="modify-certificates"></a>Ändern von Zertifikaten
<a name="ModCerts"> </a>

Wenn Sie Fragen zur Planung, um Zertifikate haben, haben wir, die im Artikel [Planen für die Mobilität für Skype für Business Server](../plan-your-deployment/mobility.md) dokumentiert. Nachdem Sie diese gelesen haben, werden Sie durch folgende Schritte geführt:
  
- Benötige ich neue Zertifikate?
    
- Anfordern neuer Zertifikate von der Zertifizierungsstelle.
    
- Aktualisieren der vorhandenen Zertifikate mit den Ersatzzertifikaten mithilfe der PowerShell.
    
- Überprüfen die Zertifikate mithilfe des Zertifikate-Snap-Ins in der Microsoft Management Console (MMC).
    
### <a name="do-i-need-new-certificates"></a>Benötige ich neue Zertifikate?

1. Zunächst müssen Sie überprüfen, welche Zertifikate in-Place sind und ob sie die Einträge besitzen, die Sie benötigen. Dazu müssen Sie in Ihrer Skype für Business Server mit einem Konto anmelden, das ein lokaler Administrator ist. Dieses Konto müssen auch Rechte an die ausstellende Zertifizierungsstelle (CA), für einige dieser Schritte haben.
    
2. Öffnen Sie die Skype für Business Server-Verwaltungsshell (Suche können Sie gefunden werden, wenn Sie fixiert zu Ihrer Startleiste Menü- oder Aufgabe nicht vorhanden ist).
    
3. Sie müssen unbedingt wissen, welche Zertifikate Ihnen zugewiesen sind, bevor Sie versuchen, ein aktualisiertes Zertifikat hinzuzufügen. Geben Sie daher an der Befehlszeile Folgendes ein:
    
   ```
   Get-CsCertificate
   ```

4. Die Informationen aus Schritt 3 sind für Sie eindeutig. Sie können Sie durchgehen, um festzustellen, ob Ihnen ein einzelnes Zertifikat für verschiedene Zwecke zugewiesen wurde, oder ob Sie über mehrere Zertifikate für die einzelnen Komponenten, die sie benötigen, verfügen. Über den Parameter **Verwendung** erfahren Sie, wie ein Zertifikat verwendet wird, und der Parameter **Fingerabdruck** gibt an, ob es sich um das gleiche Zertifikat oder mehrere Zertifikate handelt.
    
5. Wenn Sie über die in unserem Planungsabschnitt empfohlenen SAN-Einträge verfügen, ist alles in Ordnung. Falls nicht, müssen Sie ein neues Zertifikat bzw. mehrere Zertifikate (abhängig von Ihrer Konfiguration) bei der Zertifizierungsstelle beantragen.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>Anfordern eines neuen Zertifikats oder mehrerer Zertifikate von der Zertifizierungsstelle

1. Nachdem Sie geprüft haben, über welche SAN-Einträge Sie verfügen, wissen Sie, dass Sie ein **einzelnes Zertifikat** haben (nachdem Sie dies anhand der obigen Schritte geprüft haben), und dass Sie nicht über alle benötigten Einträge verfügen. Sie müssen bei Ihrer Zertifizierungsstelle ein neues Zertifikat beantragen. Öffnen Sie Ihre Skype für Business Server-PowerShell:
    
   - Für einen fehlenden AutoErmittlungsdienst-SAN (ersetzen Sie den Parameter -Ca durch den Pfad Ihrer Zertifizierungsstelle):
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Wenn Sie mehrere SIP-Domänen haben, können Sie den Parameter „AllSipDomain“ nicht wie im Beispiel oben verwenden. Sie müssen stattdessen den Parameter „DomainName“ verwenden. Und wenn Sie den Parameter „DomainName“ verwenden, müssen Sie den vollqualifizierten Domänennamen für die Einträge „lyncdiscoverinternal“ und „lyncdiscover“ definieren. Ein Beispiel wäre Folgendes (ersetzen Sie den Parameter -Ca mit dem Pfad Ihrer Zertifizierungsstelle):
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. Nachdem Sie geprüft haben, über welche SAN-Einträge Sie verfügen, wissen Sie, dass Sie **mehrere Zertifikate** haben und dass Sie nicht über alle benötigten Einträge verfügen. Sie müssen bei Ihrer Zertifizierungsstelle ein neues Zertifikat beantragen. Öffnen Sie Ihre Skype für Business Server-PowerShell:
    
   - Für einen fehlenden AutoErmittlungsdienst-SAN (ersetzen Sie den Parameter -Ca durch den Pfad Ihrer Zertifizierungsstelle):
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Wenn Sie mehrere SIP-Domänen haben, können Sie den Parameter „AllSipDomain“ nicht wie im Beispiel oben verwenden. Sie müssen stattdessen den Parameter „DomainName“ verwenden. Und wenn Sie den Parameter „DomainName“ verwenden, müssen Sie den vollqualifizierten Domänennamen für die Einträge „lyncdiscoverinternal“ und „lyncdiscover“ definieren. Ein Beispiel wäre Folgendes (ersetzen Sie den Parameter -Ca mit dem Pfad Ihrer Zertifizierungsstelle):
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - Nachdem die neuen Zertifikate von der Zertifizierungsstelle generiert wurden, müssen Sie sie zuweisen.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Zuweisen von Zertifikaten mit der Skype for Business Server-Verwaltungsshell

- Abhängig von den Ergebnissen im Abschnitt „Benötige ich neue Zertifikate“ oben müssen Sie **einen** der folgenden Befehle ausführen.
    
  - Wenn Sie ein einzelnes Zertifikat für alles haben (die Fingerabdrücke sind identisch), müssen Sie folgenden Befehl ausführen:
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - Wenn Sie verschiedene Zertifikate haben (die Fingerabdrücke sind unterschiedlich), führen Sie stattdessen folgenden Befehl aus:
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Anzeigen von Zertifikaten in der Microsoft Management Console (MMC)

1. Es gibt eine Option zum Anzeigen Ihrer Zertifikate mit dem Zertifikat-Snap-In für die MMC. Geben Sie einfach „MMC“ in das Suchfeld ein, und die Anwendungsoption wird angezeigt.
    
2. Um das Zertifikat-Snap-In hinzuzufügen, klicken Sie auf **Datei** und dann auf **Snap-In hinzufügen/entfernen...** (auch das Tastaturkürzel **Strg+M** kann verwendet werden). **Zertifikate** ist eine Option im linken Fensterbereich. Wählen Sie sie aus, und wählen Sie dann **Computerkonto** im Popup-Fenster. Klicken Sie dann auf **Weiter**.
    
3. Noch in das Popup-Fenster aller Wahrscheinlichkeit tun Sie dies auf dem Computer, die home wurde auf die betrachten, so lassen Sie den benötigten Zertifikate die Auswahl auf **lokalen Computer** so ist. Wenn Sie auf einem Remotecomputer arbeiten, ändern Sie das Optionsfeld in **Einem anderen Computer** , und klicken Sie dann geben Sie FQDN des Computers ein oder verwenden Sie die Schaltfläche **Durchsuchen** , um für diesen Computer über AD suchen. Nachdem Sie auf den Computer, müssen Sie auf **Fertig stellen** , wenn Sie bereit sind, und dann auf **OK** , um das Snap-in der MMC hinzufügen klicken.
    
4. Erweitern Sie im Abschnitt **Zertifikate** , klicken Sie im linken Bereich der MMC. Erweitern Sie auch den **persönlichen Ordner**, und wählen Sie dann **Zertifikate** aus. Damit können Sie die Zertifikate in diesem Speicher anzeigen.
    
5. Sie müssen die anzuzeigenden Zertifikate suchen, mit der rechten Maustaste darauf klicken und die Option **Öffnen** wählen.
    
    > [!NOTE]
    > Woher wissen Sie, welche Zertifikat Hierbei handelt es sich? Es sollte entweder das einzelne Zertifikat auf Alles, was für Ihre Farm zugewiesen sein oder möglicherweise mehrere Zertifikate für verschiedene Dinge wie Standard, interne Webdienste usw., in diesem Fall müssen Sie möglicherweise mehrere Zertifikate betrachten. Mehrere Zertifikate müssen denselben Fingerabdruck. 
  
6. Nachdem Sie die **Zertifikat**-Ansicht geöffnet haben, wählen Sie **Details**. Dort sehen Sie den Zertifikatantragstellernamen, wenn Sie **Antragsteller** auswählen, und der zugewiesene Antragstellername und die zugeordneten Eigenschaften werden angezeigt.
    
7. Sie müssen auch die Einträge für den **alternativen Antragstellernamen** prüfen. Dort finden Sie einen oder mehrere der folgenden Einträge:
    
   - Der Poolname für diesen Pool oder der Name des einzelnen Servers, wenn dieser keinem Pool.
    
   - Den Namen des Servers, dem das Zertifikat zugewiesen wurde.
    
   - Einfache URL-Einträge, üblicherweise „meet“ und „dialin“.
    
   - Webdienste interne und Webdienste externe Namen (beispielsweise webpool01.contoso.net, webpool01.contoso.com), basierend auf der getroffenen im Topologie-Generator und außer Kraft gesetzt Webdienste Auswahl.
    
   - Wenn bereits zugewiesen, die Lyncdiscover. \<Sipdomain\> und Lyncdiscoverinternal. \<Sipdomain\> Datensätze.
    
    Wenn mehr als ein Zertifikat zugewiesen ist, müssen Sie mehrere Zertifikate prüfen (siehe Hinweis oben).
    
8. Wenn also finden Sie Lyncdiscover. \<Sipdomain\> und Lyncdiscoverinternal. \<Sipdomain\> Datensätze, haben Sie dies bereits konfiguriert. Sie können die MMC schließen.
    
9. Wenn sie nicht zugewiesen sind, müssen Sie entweder ein neues Zertifikat beantragen stellen (wie oben beschrieben) oder die Zertifikate nach dem Antrag installieren (es wird empfohlen, hierfür wie oben beschrieben PowerShell zu verwenden).
    
## <a name="configure-the-reverse-proxy"></a>Konfigurieren des Reverseproxys
<a name="ConfigRP"> </a>

Die folgenden Schritte sind nicht zur exakten Befolgung gedacht. In früheren Produktversionen wurden Sie beispielsweise durch die Konfiguration von Threat Management Gateway (TMG) geführt, und wenn Sie dies nicht verwendeten, mussten Sie von dieser Stelle an Ihre eigene Version erarbeiten.
  
TMG ist nicht mehr von Microsoft als Produkt angeboten wird, und wenn Sie weiterhin konfigurieren müssen, können Sie die [Lync Server 2013 Schritte](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx)betrachten. Jedoch die folgende Informationen des für die direkte Verwendung im Allgemeinen empfiehlt sich, auch wenn es besteht keine Möglichkeit, die wir für jede Reverseproxy gibt es bestimmte Arbeitsschritte bereitstellen können.
  
Es sind zwei Hauptpunkte zu berücksichtigen:
  
- Möchten Sie die anfängliche AutoErmittlung-Anforderung über HTTPS stellen (empfohlen)?
    
  - Wenn Sie über eine Webveröffentlichungsregel verfügen, müssen Sie diese ändern.
    
  - Wenn Sie noch nicht über eine Webveröffentlichungsregel verfügen, müssen Sie eine erstellen.
    
- Wenn Sie die anfängliche AutoErmittlung-Anforderung über HTTP stellen, müssen Sie diese Regel ebenfalls erstellen oder ändern.
    
> [!NOTE]
> **Wichtige** Ein Proxy Timeoutwert ist eine Zahl, die Bereitstellung auf Bereitstellung variieren. Überwachen die Bereitstellung, und ändern Sie den Wert für die beste Lösung für Clients. Sie können den Wert so niedrig wie 200 festlegen können. Wenn Sie mobile Lync-Clients in Ihrer Umgebung unterstützen, sollten Sie den Wert auf 960 von Office 365, damit Push Notification Timeouts kann festlegen, die einen Timeoutwert von 900 verfügen. Es ist sehr wahrscheinlich, dass Sie, erhöhen Sie den Timeoutwert zum Vermeiden von Client müssen getrennt wird, wenn der Wert zu niedrig ist, oder verringern Sie die Anzahl Verbindungen über den Proxy nicht trennen jedoch nicht löschen, lange, nachdem der Client getrennt wurde. Überwachung und Baseline für was üblichen für Ihre Umgebung ist, ist die einzige exakte Möglichkeit für die entsprechende Einstellung für diesen Wert zu bestimmen.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Bearbeiten einer bestehenden Webveröffentlichungsregel für den externen AutoErmittlungsdienst-SAN und die -URL

1. Öffnen Sie Ihre reverseproxyschnittstelle.
    
2. Sie müssen suchen die Webveröffentlichungsregel, und wählen die Option bearbeiten (möglicherweise in einem Menü oder Registerkarte, je nach der Konfiguration des Reverseproxys sein).
    
3. Es sollte ein Bereich, der besagt, was diese Webveröffentlichungsregel auf angewendet wird. Sie müssen diese Regel für eingehende Websites oder Anforderungen für Websites ändern. Dafür müssen Sie einen neuen Eintrag **hinzufügen**.
    
4. Geben Sie den Namen der Website für die AutoErmittlung (wir verwenden Beispiel ist "lyncdiscover.contoso.com"), und klicken Sie auf **OK** oder **Speichern**, je nach Ihren Reverseproxy aufrufen Format.
    
5. Möglicherweise verfügen Sie über ein neues Zertifikat mit dem SAN-Eintrag für AutoErmittlung. Die ebenfalls installiert und für die Verwendung entsprechend Ihren Reverseproxy aufrufen Einstellungen konfiguriert werden muss. Vergessen Sie nicht, alles zu speichern, wenn die Konfiguration abgeschlossen ist.
    
6. Wenn Ihren Reverseproxy Aufrufen eine **Test** -Funktionalität aufweist, klicken Sie dann stellen sich, um sicherzustellen, dass alles ordnungsgemäß funktioniert.
    
7. Nun, Sie möchten diese Schritte wiederholen, wenn Sie einen Director oder Director haben Pools in Ihrer Umgebung (dazu müssen Sie eine zweite Regel haben).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Erstellen Sie eine Webveröffentlichungsregel für die externe AutoErmittlungsdienst-URL

1. Öffnen Sie Ihre reverseproxyschnittstelle.
    
2. Sie müssen suchen, in dem in der Benutzeroberfläche Ihrer Webveröffentlichungsregeln zu erstellen, und wählen Sie die Option **neu** oder **Erstellen** (möglicherweise in einem Menü oder Registerkarte, je nach der Konfiguration des Reverseproxys sein). Suchen Sie nach der Option zum Erstellen einer neuen Webveröffentlichungsregel.
    
3. In der Regel müssen Sie folgende Informationen eingeben:
    
   - **Name**: der Name Ihrer Regel
    
   - **Regelaktion**: In diesem Fall ist es einer Regel zum **gewähren** , lassen Sie etwas über den Reverseproxy geleitet.
    
   - Die Regel oder Option für die **Veröffentlichung**, die Sie auswählen, ist **einzelne Website oder Lastenausgleich**.
    
   - Für externen Zugriff muss es sich um **SSL** handeln; wählen Sie diese Option.
    
   - Sie müssen einen Pfad für **Interne Publishing**veröffentlichen, und geben Sie den FQDN für die externe Webdienste auf dem System zum Lastenausgleich der Front-End-Pool (oder den FQDN des Director-Pool System zum Lastenausgleich, sofern vorhanden) nun, ein Beispiel wäre sfb_ pool01.contoso.Local.
    
   - Geben Sie ** / ** wie den Pfad zu veröffentlichenden, aber Sie auch **den ursprünglichen Hostheader**weiterleiten müssen.
    
   - Sie finden eine Option für Details oder Informationen zum **öffentlichen oder externen Namen**. Dort können Sie Folgendes eingeben:
    
   - **Anforderungen akzeptieren**, dies sollte aber für den Domänennamen geschehen.
    
   - Geben Sie als **Namen** den Wert **lyncdiscover.** <sipdomain>(Dies ist die externe AutoErmittlungsdienst-URL). Wenn Sie eine Regel für die externen Webdienste-URL auf den Front-End-Pool erstellen, müssen Sie jetzt, geben Sie den FQDN für die externe Webdienste auf dem Front-End-Pool (beispielsweise lyncwebextpool01.contoso.com).
    
   - Wird eine Option **Pfad** vorhanden sein, und Sie müssen eingeben ** / ** hier.
    
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

1. Öffnen Sie Ihre reverseproxyschnittstelle.
    
2. Sie müssen suchen, in dem in der Benutzeroberfläche Ihrer Webveröffentlichungsregeln zu erstellen, und wählen Sie die Option **neu** oder **Erstellen** (möglicherweise in einem Menü oder Registerkarte, je nach der Konfiguration des Reverseproxys sein). Suchen Sie nach der Option zum Erstellen einer neuen Webveröffentlichungsregel.
    
3. In der Regel müssen Sie folgende Informationen eingeben:
    
   - **Name**: der Name Ihrer Regel
    
   - **Regelaktion**: In diesem Fall ist es einer Regel zum **gewähren** , lassen Sie etwas über den Reverseproxy geleitet.
    
   - Die Regel oder Option für die **Veröffentlichung**, die Sie auswählen, ist **einzelne Website oder Lastenausgleich**.
    
   - Dabei muss es sich um eine **nicht gesicherte Verbindung zur Verbindung mit dem veröffentlichten Webserver bzw. der Farm handeln**.
    
   - Sie müssen einen Pfad für **Interne Publishing**veröffentlichen, und geben Sie den FQDN für die **VIP-Adresse** des Systems zum Lastenausgleich für den Front-End-Pool nun, ein Beispiel wäre sfb_pool01.contoso.local.
    
   - Geben Sie ** / ** wie den Pfad zu veröffentlichenden, aber Sie auch **den ursprünglichen Hostheader**weiterleiten müssen.
    
   - Sie finden eine Option für Details oder Informationen zum **öffentlichen oder externen Namen**. Dort können Sie Folgendes eingeben:
    
   - **Anforderungen akzeptieren**, dies sollte aber für den Domänennamen geschehen.
    
   - Geben Sie als **Namen** den Wert **lyncdiscover.** <sipdomain>(Dies ist die externe AutoErmittlungsdienst-URL).
    
   - Wird eine Option **Pfad** vorhanden sein, und Sie müssen eingeben ** / ** hier.
    
   - Sie müssen einen Weblistener oder Ihren Reverseproxy Aufrufen eines für Sie erstellen können.
    
   - **Authentifizierungsdelegierung** muss auf **Keine Delegierung** festgelegt sein, aber direkte Clientauthentifizierung **darf nicht** zulässig sein.
    
   - Diese Regel muss auf **Alle Benutzer** festgelegt werden.
    
   - Das dürften alle Informationen sein, die Sie zum Erstellen dieser Regel benötigen, damit Sie fortfahren können.
    
4. Die **Webserver**-Ports müssen festgelegt werden. Gehen Sie wie folgt vor:
    
   - **Leiten Sie Anforderungen an den HTTP-Port weiter**. Die Portnummer muss **8080** lauten.
    
   - **Leiten Sie Anforderungen an den SSL-Port weiter**. Die Portnummer muss **4443** lauten.
    
5. Wenn alles konfiguriert ist, müssen Sie die Optionen speichern oder anwenden und sollten die Regel dann testen.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Konfigurieren der AutoErmittlung für Mobilität mit Hybridbereitstellungen
<a name="ConfigAutoD"> </a>

Hybridumgebungen in Skype für Business Server sind Umgebungen, die einem lokalen kombinieren und Office 365-Umgebung. Wenn Sie Skype für Business Server funktioniert in einer hybridumgebung haben, muss der AutoErmittlungsdienst nach einem Benutzer von einer der folgenden Umgebungen suchen können.
  
Damit Mobilclients ermitteln können, wo sich ein Benutzer befindet, muss der AutoErmittlungsdienst mit einem neuen Uniform Resource Locator (URL) konfiguriert sein. Führen Sie folgende Schritte aus:
  
1. Öffnen Sie Skype für Business Server-Verwaltungsshell.
    
2. Führen Sie Folgendes ein, um den Wert des **proxyfqdn** für Ihre Skype für Business Server-Umgebung zu erhalten:
    
  ```
  Get-CsHostingProvider
  ```

3. Führen Sie dann im Shellfenster folgenden Befehl aus:
    
  ```
  Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
  ```

    Hierbei wird [identity] durch den Domänennamen des freigegebenhen SIP-Adressraums ersetzt.
    
## <a name="test-your-mobility-deployment"></a>Testen der Mobilitätsbereitstellung
<a name="TestMobility"> </a>

Nachdem Sie Skype Business Server-Mobilitätsdienst und Skype für Business Server AutoErmittlungsdienst bereitgestellt haben, sollten Sie eine Testtransaktion, um rechten stellen Sie sicher, dass Ihre Bereitstellung arbeiten ausführen. Sie können **Test-CsUcwaConference** ausführen, um die Fähigkeit zweier Benutzer zu testen, eine Konferenz zu erstellen, daran teilzunehmen und darin zu kommunizieren. Sie benötigen zwei Benutzer (echte oder Testbenutzer) und deren vollständige Anmeldeinformationen für diesen Test. Mit diesem Befehl wird für beide Skype für Business Clients als auch für Lync Server 2013-Clients verwendet werden.
  
Für Lync Server 2010-Clients auf Skype für Business Server 2015 müssen Sie führen Sie **Test-CsMcxP2PIM** zu testen. Die Lync Server 2010-Benutzer müssen weiterhin tatsächlichen Benutzern oder vordefinierten Testbenutzer sein und benötigen Sie ihre Anmeldeinformationen.

> [!NOTE]
> MCX-Unterstützung für mobile Clients von Vorversionen ist nicht mehr in Skype für Business Server 2019 verfügbar. Die Benutzer müssen an einen aktuellen Client aktualisieren.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Testkonferenz für Skype for Business- und Lync 2013-Mobilclients

1. Melden Sie sich als Mitglied der **CsAdministrator** -Rolle auf einem beliebigen Computer, auf dem **Skype für Business Server-Verwaltungsshell** und **Ocscore** installiert sind.
    
2. Starten Sie die **Skype für Business Server-Verwaltungsshell** (Sie möglicherweise Geben Sie den Namen bei der Suche oder zeigen Sie auf **Alle Programme** und auswählen).
    
3. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   Sie können auch Anmeldeinformationen in einem Skript festlegen und sie an das Test-Cmdlet übergeben. Dafür sehen Sie unten ein Beispiel.
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Konferenztest für Lync 2010-Mobilclients

> [!NOTE]
> MCX-Unterstützung für mobile Clients von Vorversionen ist nicht mehr in Skype für Business Server 2019 verfügbar. Die Benutzer müssen an einen aktuellen Client aktualisieren.

1. Melden Sie sich als Mitglied der **CsAdministrator** -Rolle auf einem beliebigen Computer, auf dem **Skype für Business Server-Verwaltungsshell** und **Ocscore** installiert sind.
    
2. Starten Sie die **Skype für Business Server-Verwaltungsshell** (Sie möglicherweise Geben Sie den Namen bei der Suche oder zeigen Sie auf **Alle Programme** und auswählen).
    
3. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   Sie können auch Anmeldeinformationen in einem Skript festlegen und sie an das Test-Cmdlet übergeben. Dafür sehen Sie unten ein Beispiel.
    
  ```
  $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
  $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
  $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
  $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
  Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
  ```

Um den Befehl Verfahren überprüfen können darüber hinaus [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) "und" [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)ausgecheckt werden.
  
## <a name="configure-for-push-notifications"></a>Konfigurieren von Pushbenachrichtigungen
<a name="ConfigPush"> </a>

Pushbenachrichtigungen in Form von Badges, Symbolen oder Warnungen können an ein Mobilgerät gesendet werden, selbst wenn die Skype- oder Lync-App inaktiv ist. Aber was sind Pushbenachrichtigungen? Dabei handelt es sich um Ereignisbenachrichtigungen, wie neue oder verpasste Chateinladungen oder eine erhaltene Voicemail. Die Skype für Business Server-mobilitätsdienst sendet diese Benachrichtigungen an die Cloud-basierten Skype für Business Server Push Notification Service, der Sie dann die Benachrichtigungen zu Microsoft Push Notification Service (MSNS) für Windows Phone-Benutzer sendet.
  
Diese Funktionalität wird von Lync Server 2013 nicht geändert, aber wenn Sie einen Skype für Business Server verfügen, sollten Sie folgende Aktionen ausführen:
  
- Für einen Skype für Business Server-Edgeserver einen neuen Hostinganbieter, Microsoft Skype für Business Online, hinzufügen, und klicken Sie dann Hostinganbieter-Partnerverbund zwischen Ihrer Organisation und Skype für Business Online einrichten.
    
- Aktivieren Sie Pushbenachrichtigungen, indem Sie das Cmdlet **Set-CsPushNotificationConfiguration** ausführen. Pushbenachrichtigungen sind standardmäßig deaktiviert.
    
- Testen Sie die Partnerverbundkonfiguration und die Pushbenachrichtigungen.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Konfigurieren des Skype for Business Edge Server für Pushbenachrichtigungen

1. Melden Sie sich, mit einem Konto, das Mitglied der Rolle **"csadministrator"** an einem Computer ist, auf dem **Skype für Business Server-Verwaltungsshell** und **Ocscore** installiert sind.
    
2. Starten Sie die **Skype für Business Server-Verwaltungsshell**.
    
3. Fügen Sie einen Skype für online Hostinganbieter Business Server hinzu.
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Beispiel:
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > Es kann nur maximal eine Partnerverbundbeziehung mit einem einzelnen Hostinganbieter bestehen. Wenn Sie also bereits einen Hostinganbieter eingerichtet haben, der eine Partnerverbundbeziehung mit „sipfed.online.lync.com“ hat, fügen Sie keinen weiteren Hostinganbieter hinzu, auch wenn die Identität des Hostinganbieters nicht „LyncOnline“ ist. 
  
4. Richten Sie den hostinganbieterverbund zwischen Ihrer Organisation und das Push Notification Service unter Skype für Business Online. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Aktivieren von Pushbenachrichtigungen

1. Melden Sie sich, mit einem Konto, das Mitglied der Rolle **"csadministrator"** an einem Computer ist, auf dem **Skype für Business Server-Verwaltungsshell** und **Ocscore** installiert sind.
    
2. Starten Sie die **Skype für Business Server-Verwaltungsshell**.
    
3. Aktivieren Sie Pushbenachrichtigungen:
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Aktivieren Sie den Partnerverbund:
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>des Partnerverbunds und der Pushbenachrichtigungen

1. Melden Sie sich, mit einem Konto, das Mitglied der Rolle **"csadministrator"** an einem Computer ist, auf dem **Skype für Business Server-Verwaltungsshell** und **Ocscore** installiert sind.
    
2. Starten Sie die **Skype für Business Server-Verwaltungsshell**.
    
3. Testen Sie die Partnerverbundkonfiguration:
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    Beispiel:
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. Testen Sie die Pushbenachrichtigungen:
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    Beispiel:
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>Konfigurieren der Mobilitätsrichtlinie
<a name="ConfigMob"> </a>

Sie haben die Möglichkeit mit Skype für Business Server, um zu bestimmen, wer Ihre mobilitätsdienst verwenden können, rufen Sie über den Arbeitsplatz, Voice over IP (VoIP) oder Video, sowie, ob WiFi für VoIP oder Video erforderlich sein soll. Mit der Funktion „Geschäftlich anrufen“ kann ein Benutzer Anrufe auf seinem Mobiltelefon unter Verwendung seiner geschäftlichen Telefonnummer anstatt seiner Mobilfunknummer tätigen und entgegennehmen. Der Gesprächspartner kann die Mobiltelefonnummer dieses Mobilbenutzers nicht sehen, und der Mobilbenutzer kann damit ausgehende Anrufgebühren vermeiden. Wenn VoIP und Video eingerichtet sind, können Benutzer VoIP-Anrufe annehmen und tätigen und Video nutzen. Mit den Einstellungen für WLAN-Nutzung wird festgelegt, ob das Mobilgerät eines Benutzers ein WLAN-Netzwerk über ein mobiles Datennetzwerk nutzen muss.
  
Features für Mobilität, Anruf über den Arbeitsplatz, und die VoIP und video sind alle standardmäßig aktiviert. Die Einstellungen, die WLAN für VoIP und Video erfordern, sind deaktiviert. Administratoren können dies entweder global, nach Standort oder nach Benutzer ändern.
  
Um die Mobilitätsfeatures und anrufen verwenden zu können über den Arbeitsplatz, Benutzer werden müssen:
  
- Für Skype aktiviert für Business Server
    
- Aktiviert für Enterprise-VoIP
    
- Zugewiesen eine mobilitätsrichtlinie, die die Option **EnableMobility** auf **True**festgelegt wurde.
    
Damit Benutzer die Funktion „Geschäftlich anrufen“ verwenden können, muss auf sie zudem Folgendes zutreffen:
  
- Ihnen muss eine VoIP-Richtlinie zugewiesen sein, für die die Option **Gleichzeitiges Klingeln von Telefonen aktivieren** aktiviert ist.
    
- Zugewiesen eine mobilitätsrichtlinie, die die **EnableOutsideVoice** auf **True**festgelegt wurde.
    
> [!NOTE]
> Benutzer, die nicht für Enterprise-VoIP aktiviert sind, können mithilfe ihrer Mobilgeräte VoIP-Anrufe zwischen Skype-Benutzern tätigen oder an Konferenzen teilnehmen, indem sie auf ihrem mobilen Gerät den Link „Zum Beitreten klicken“ nutzen. Hierzu müssen die entsprechenden Optionen für die VoIP-Richtlinie, der sie zugeordnet sind, festgelegt sein. Weitere Informationen finden Sie im Planungsthema. 
  
### <a name="modify-global-mobility-policy"></a>Ändern der globalen Mobilitätsrichtlinie

1. Melden Sie sich, mit einem Konto, das Mitglied der Rolle **"csadministrator"** an einem Computer ist, auf dem **Skype für Business Server-Verwaltungsshell** und **Ocscore** installiert sind.
    
2. Starten Sie die **Skype für Business Server-Verwaltungsshell**.
    
3. Deaktivieren des Zugriffs auf Mobilität und "geschäftlich anrufen" Global durch eingeben:
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Sie können über Arbeitsplatz anrufen deaktivieren, ohne Zugriff auf Mobilität auszuschalten. Jedoch können nicht deaktiviert werden Mobilität ohne auch über Arbeitsplatz anrufen auszuschalten. 
  
    Checken Sie [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps), um weitere Informationen.
    
### <a name="modify-mobility-policy-by-site"></a>Ändern Sie die mobilitätsrichtlinie nach Standort

1. Melden Sie sich, mit einem Konto, das Mitglied der Rolle **"csadministrator"** an einem Computer ist, auf dem **Skype für Business Server-Verwaltungsshell** und **Ocscore** installiert sind.
    
2. Starten Sie die **Skype für Business Server-Verwaltungsshell**.
    
3. Sie können eine Richtlinie auf Standortebene erstellen, den Zugriff auf VoIP und Video deaktivieren und je nach Standort die Einstellungen aktivieren, die WLAN für IP-Audio und -Video erfordern. Geben Sie Folgendes ein:
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Weitere Informationen finden Sie unter [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-user"></a>Ändern Sie die mobilitätsrichtlinie nach Benutzer

1. Melden Sie sich, mit einem Konto, das Mitglied der Rolle **"csadministrator"** an einem Computer ist, auf dem **Skype für Business Server-Verwaltungsshell** und **Ocscore** installiert sind.
    
2. Starten Sie die **Skype für Business Server-Verwaltungsshell**.
    
3. Erstellen Benutzer Richtlinien auf Benutzerebene Mobilität und Deaktivieren von Mobilität und Anruf über den Arbeitsplatz durch Benutzer. Geben Sie Folgendes ein:
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    Ein weiteres Beispiel mit Beispieldaten:
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > Sie können über Arbeitsplatz anrufen deaktivieren, ohne Zugriff auf Mobilität auszuschalten. Jedoch können nicht deaktiviert werden Mobilität ohne auch über Arbeitsplatz anrufen auszuschalten. 
  

