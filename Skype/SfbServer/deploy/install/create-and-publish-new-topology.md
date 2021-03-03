---
title: Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 451c41a1-b8c5-4dc3-9e48-0da9ed5381a1
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie eine neue Topologie erstellen, veröffentlichen und überprüfen, bevor Sie Skype for Business Server installieren. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation Center unter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server herunter.'
ms.openlocfilehash: c18d0340c48a8bf07771d0892bed4d0740c63186
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812145"
---
# <a name="create-and-publish-new-topology-in-skype-for-business-server"></a>Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie eine neue Topologie erstellen, veröffentlichen und überprüfen, bevor Sie Skype for Business Server installieren. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation Center unter: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) herunter.
  
Bevor Sie das Skype for Business Server System auf jedem Server in der Topologie installieren können, müssen Sie eine Topologie erstellen und veröffentlichen. Wenn Sie eine Topologie veröffentlichen, laden Sie die Topologieinformationen in die Datenbank des zentralen Verwaltungsspeichers. Wenn es sich um einen Enterprise Edition-Pool handelt, erstellen Sie die Datenbank des zentralen Verwaltungsspeichers, wenn Sie zum ersten Mal eine neue Topologie veröffentlichen. Wenn dies Standard Edition ist, müssen Sie den Prozess "Ersten Standard Edition-Server vorbereiten" im Bereitstellungsassistenten ausführen, bevor Sie eine Topologie veröffentlichen. Dadurch wird die Standard Edition vorbereitet, indem eine SQL Server Express Edition installiert und der zentrale Verwaltungsspeicher erstellt wird. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der Reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm beschrieben. Das Erstellen und Veröffentlichen einer neuen Topologie wird in Schritt 6 von 8 beschrieben.
  
![Übersichtsdiagramm](../../media/c5c09ba2-c98b-4194-9857-7c3087c5560e.png)
  
## <a name="create-and-publish-new-topology"></a>Erstellen und Veröffentlichen einer neuen Topologie

Sie können den Skype for Business Server-Topologie-Generator zum Entwerfen, Definieren, Konfigurieren und Veröffentlichen von Topologien verwenden. Dieses Tool wurde bei der Installation der Verwaltungstools weiter oben in diesem Artikel installiert. Beim Erstellen einer Topologie können Sie viele verschiedene Optionen treffen. In diesem Verfahren erstellen Sie eine Basistopologie mit Konferenzen.
  
> [!IMPORTANT]
> Skype for Business Server erfordert SQL Server für den Betrieb. Die primären Datenbanken werden als zentraler Verwaltungsspeicher bezeichnet. Wenn Sie Enterprise Edition bereitstellen, werden diese Datenbanken erstellt, wenn Sie die Topologie mithilfe der folgenden Schritte veröffentlichen. In diesem Fall werden Sie vom Topologie-Generator nach den Verbindungsinformationen zu einer SQL Server gefragt. Wenn Sie die Bereitstellung der Standard Edition planen, müssen Sie SQL Server Express Edition installieren, bevor Sie die neue Topologie definieren und veröffentlichen. Um SQL Server Express Edition zu installieren, öffnen Sie den Bereitstellungsassistenten auf dem Server, der als Front-End-Server fungieren soll, und führen Sie dann "Prepare First Standard Edition Server" aus. Wenn Sie auf "Ersten Standard Edition-Server vorbereiten" klicken, installiert der Bereitstellungsassistent automatisch SQL Server Express Edition und erstellt die Datenbanken des zentralen Verwaltungsspeichers. 
  
### <a name="create-a-new-topology"></a>Erstellen einer neuen Topologie

1. Melden Sie sich als Standardbenutzer mit Zugriff auf den Topologie-Generator an.
    
2. Öffnen Sie den Skype for Business Server-Topologie-Generator.
    
3. Wählen **Sie "Neue Topologie"** aus, und klicken Sie **auf "OK".**
    
4. Wählen Sie einen Speicherort und Dateinamen für die Topologiekonfigurationsdatei aus.
    
    > [!NOTE]
    > Die Topologiekonfiguration wird als Topologie-Generator-XML-Datei (TBXML) gespeichert. Wenn Sie eine Topologie veröffentlichen, werden die Konfigurationsinformationen aus der Datei in die SQL Server werden. Wenn Sie den Topologie-Generator zukünftig öffnen, können Sie die vorhandene Konfiguration von SQL Server direkt in den Topologie-Generator herunterladen und sie entweder wieder in SQL Server veröffentlichen oder als Konfigurationsdatei des Topologie-Generators speichern. 
  
5. Geben Sie **auf dem Bildschirm "Primäre Domäne definieren"** die primäre SIP-Domäne ein, und klicken Sie auf  **"Weiter".** In diesem Beispiel verwenden wir **"contoso.local",** wie in der Abbildung dargestellt.
    
     ![Definieren Sie die primäre SIP-Domäne.](../../media/353e6b38-485f-4042-8585-aefa6c74b554.png)
  
6. Fügen Sie weitere unterstützte SIP-Domänen hinzu, und klicken Sie dann auf **"Weiter".**
    
7. Geben Sie **einen Namen** und **eine Beschreibung** für den ersten Standort ein, und klicken Sie dann auf **"Weiter",** wie in der Abbildung dargestellt.
    
     ![Definieren Sie die erste Website (Position).](../../media/d8b6c54a-2011-4efb-97fb-a4de0f11303c.png)
  
8. Geben Sie **den Ort,** **das Bundesland/Kanton** und **den Länder-/Regionalcode** für den Standort ein, und klicken Sie dann auf **"Weiter".**
    
9. Klicken **Sie auf "Fertig** stellen", um die Definition einer neuen Topologie zu beenden. Der Neue Front-End-Assistent wird automatisch gestartet.
    
### <a name="define-a-front-end-pool-or-standard-edition-server"></a>Definieren eines Front-End-Pools oder Standard Edition-Servers

1. Überprüfen Sie die Voraussetzungen des Assistenten, und klicken Sie dann auf **"Weiter".**
    
2. Geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools ein, wählen Sie entweder **enterprise Edition-Front-End-Pool** oder **Standard Edition-Server** aus, und klicken Sie dann auf "Weiter", wie in der Abbildung dargestellt.
    
    > [!TIP]
    > Skype for Business Server Enterprise Edition kann mehrere Server umfassen, die zusammenarbeiten, um die Front-End-Rolle zu bieten. Wenn mehrere Server verwendet werden, um die Rolle zu erfüllen, wird sie als Pool bezeichnet. Daher werden mehrere Server, die gemeinsam die Front-End-Rolle bereitstellen, auch als Front-End-Pool bezeichnet. Skype for Business Server Standard Edition kann nur einen einzigen Server enthalten, um die Front-End-Rolle zur Verfügung zu stellen. Es ist üblich, auf den Front-End-Pool zu verweisen, auch wenn nur ein einzelner Server die Rolle übernimmt. 
  
     ![Definieren Sie den Front-End-Pool.](../../media/c1447557-261e-4260-a362-ab8d19070eb9.png)
  
3. Geben Sie die vollqualifizierten Domänennamen (Fully Qualified Domain Names, FQDNs) aller Computer im Pool ein, und klicken Sie dann auf "Weiter",  wie in der Abbildung dargestellt.
    
     ![Definieren Sie die Computer im Pool.](../../media/1106b4f3-8745-485b-b495-f885a5dfefda.png)
  
4. Wählen Sie die Features aus, die in dieser  Topologie enthalten sein sollen, und klicken Sie dann auf "Weiter", wie in der Abbildung dargestellt.
    
    > [!NOTE]
    > Skype for Business Server umfasst viele erweiterte Funktionen. Lesen Sie die Planungs- und Bereitstellungsdokumentation für jedes feature, das Sie verwenden möchten. 
  
     ![Wählen Sie Features für die Bereitstellung aus.](../../media/77257588-d0e1-4517-a12a-869ffe009353.png)
  
5. Auf **der** Seite "Verbindende Serverrollen auswählen" können Sie den Vermittlungsserver auf dem Front-End-Server verbinden oder ihn als eigenständigen Server bereitstellen.
    
    Wenn Sie den Vermittlungsserver im Front-End-Pool der Enterprise Edition verbinden möchten, stellen Sie sicher, dass das Kontrollkästchen aktiviert ist. Die Serverrolle wird auf den Poolservern bereitgestellt. Wenn Sie den Vermittlungsserver als eigenständigen Server bereitstellen möchten, müssen Sie das entsprechende Kontrollkästchen aktivieren. Nach der vollständigen Bereitstellung des Front-End-Servers stellen Sie den Vermittlungsserver in einem separaten Bereitstellungsschritt zur Bereitstellung zur Bereitstellung. Einzelheiten zur Planung einer Kollokation finden Sie unter [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md).
    
6. Mithilfe der Seite **"Serverrollen dieser Front-End-Poolseite** zuordnen" können Sie Serverrollen definieren und dem Front-End-Pool zuordnen. Die folgende Rolle ist verfügbar:
    
    **Aktivieren eines Edgepools** Definiert und ordnet einen einzelnen Edgeserver oder einen Pool von Edgeservern zu. Ein Edgeserver erleichtert die Kommunikation und Zusammenarbeit zwischen Benutzern innerhalb der Organisation und Personen außerhalb der Organisation, einschließlich Verbundbenutzern.
    
    Es gibt zwei mögliche Szenarien, die Sie zum Bereitstellen und Zuordnen der Serverrollen verwenden können.
    
    In Szenario 1 definieren Sie eine neue Topologie für eine Neuinstallation. Sie können die Installation auf eine der beiden folgenden Arten verwenden:
    
   - Lassen Sie das Kontrollkästchen nicht, und definieren Sie die Topologie. Nachdem Sie die Front-End- und Back-End-Serverrollen veröffentlicht, konfiguriert und getestet haben, können Sie den Topologie-Generator erneut ausführen, um die Rollenserver der Topologie hinzuzufügen. Mit dieser Strategie können Sie den Front-End-Pool und den Server, auf dem SQL Server zusätzliche Rollen ausführen, ohne komplikationslos testen. Nachdem Sie die ersten Tests abgeschlossen haben, können Sie den Topologie-Generator erneut ausführen, um die Rollen auszuwählen, die Sie bereitstellen müssen.
    
   - Wählen Sie die Rollen aus, die installiert werden müssen, und richten Sie anschließend die Hardware für die ausgewählten Rollen ein.
    
     Für Szenario 2 verfügen Sie über eine vorhandene Bereitstellung, und Ihre Infrastruktur ist für neue Rollen bereit, oder Sie müssen vorhandene Rollen einem neuen Front-End-Server zuordnen.
    
   - In diesem Fall wählen Sie die Rollen aus, die Sie bereitstellen oder dem neuen Front-End-Server zuordnen möchten. In beiden Fällen fahren Sie mit der Definition der Rollen fort, richten gegebenenfalls erforderliche Hardware ein und führen die Installation aus.
    
7. Als Nächstes definieren Sie den SQL Server, der mit der Topologie verwendet wird. In diesem Beispiel wird die Standardinstanz verwendet. Weitere Informationen zu den SQL Server, z. B. hohe Verfügbarkeit, finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
    
   - Zum Verwenden eines vorhandenen SQL Server-Speichers, der bereits in Ihrer Topologie definiert wurde, wählen Sie eine Instanz unter **SQL-Speicher** aus.
    
   - Um eine neue SQL Server zum Speichern von Poolinformationen zu definieren, klicken Sie auf "Neu", und geben Sie dann den **FQDN SQL Server** im Dialogfeld "Neuen SQL Speicher definieren" an.  
    
   - Zum Angeben des Namens einer SQL Server-Instanz wählen Sie **Benannte Instanz**, und geben Sie anschließend den Namen der Instanz an.
    
   - Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden.
    
   - Wenn Sie die SQL verwenden möchten, wählen Sie "SQL Spiegelung aktivieren" **aus,** und wählen Sie eine vorhandene Instanz aus, oder erstellen Sie eine neue Instanz.

     > [!NOTE]
     > SQL Spiegelung ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. Die Methoden für AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen (FCI) und SQL-Failoverclustering werden mit Skype for Business Server 2019 bevorzugt.
    
     In diesem Beispiel geben wir den SQL Server **FQDN** ein, konfigurieren alle relevanten Hochverfügbarkeitseinstellungen und klicken dann auf **"OK",** wie in der Abbildung dargestellt.
    
     ![Erstellen Sie einen SQL Server Speicher.](../../media/12822cf9-8608-43c0-94ce-2ca8b3a0ffd5.png)
  
8. Entscheiden Sie, ob Sie die SQL Server oder SQL Server Aktivieren des Spiegelungszeugen aktivieren möchten, und klicken Sie dann auf **"Weiter".**
    
9. Definieren Sie die Dateifreigabe, die Sie verwenden möchten.
    
   - Zum Verwenden einer Dateifreigabe, die bereits in Ihrer Topologie definiert wurde, wählen Sie **Zuvor definierte Dateifreigabe verwenden**.
    
   - Zum Definieren einer neuen Dateifreigabe wählen Sie **Neue Dateifreigabe definieren**, geben Sie im Feld **Dateiserver-FQDN** den vollqualifizierten Domänennamen des vorhandenen Dateiservers ein, auf dem sich die Dateifreigabe befinden soll, und geben Sie anschließend einen Namen für die Dateifreigabe in das Feld **Dateifreigabe** ein.
    
     In diesem Beispiel klicken wir auf "Neuen Dateispeicher **definieren",** geben den **Dateiserver-FQDN** und die Dateifreigabe ein, und klicken Sie dann auf **"Weiter".**
    
     > [!NOTE]
     > Die Dateifreigabe für Skype for Business Server kann gemeinsam ausgeführt werden, wird jedoch aus Leistungsgründen nicht empfohlen. Beachten Sie, dass sich die Dateifreigabe in diesem Beispiel auf einem einzelnen dedizierten Server befindet, der als Dateifreigabe fungieren wird. Es werden jedoch andere robustere Dateisysteme empfohlen, z. B. DFS mit Windows Server 2012 R2. Weitere Informationen zu unterstützten Dateifreigabesystemen finden Sie unter ["Anforderungen für Ihre Skype for Business-Umgebung".](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) Weitere Informationen zum Erstellen der Dateifreigabe finden Sie unter [Erstellen einer Dateifreigabe in Skype for Business Server](create-a-file-share.md). Sie können die Dateifreigabe definieren, ohne dass die Dateifreigabe erstellt wurde. Sie müssen die Dateifreigabe am definierten Speicherort erstellen, bevor Sie die Topologie veröffentlichen. 
  
10. Auf der Seite "Webdienste-URL angeben" müssen Sie entscheiden, ob Sie die Basis-URL des internen Webdienstepools außer Kraft setzen müssen. Der Grund für diese Außerkraftsetzung liegt im Lastenausgleich. Grundlegender SIP-Datenverkehr kann über einen einfachen DNS-Lastenausgleich lastenausgleich verwendet werden. Der HTTP/S-Webdienste-Netzwerkdatenverkehr muss jedoch eine unterstützte Hardware- oder Softwarelösung für den Lastenausgleich verwenden. Unterstützte Lastenausgleichssetter finden Sie [unter "Infrastruktur für Skype for Business".](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) In diesem Beispiel haben wir den DNS-Lastenausgleich für den SIP-Datenverkehr und eine unterstützte Lösung für den Softwarelastenausgleich verwendet. Da der Datenverkehr auf diese Weise geteilt wird, müssen wir den internen FQDN des Webdienstepools außer Kraft setzen. Alternativ müssten wir die Webdienste-URL nicht außer Kraft setzen, wenn wir einen Lastenausgleich für die erste Zeile verwenden und den datenverkehrsunserladenden Datenverkehr durch das Lastenausgleichsgerät gesendet haben, anstatt den DNS-Lastenausgleich für den SIP-Datenverkehr zu verwenden. 
    
    Im Abschnitt "DNS" dieses Themas haben wir einen A-Eintrag für "webint.contoso.local" erstellt. Dies ist die URL, die wir für den HTTP/S-Datenverkehr der Webdienste verwenden, und sie muss den unterstützten Softwarelastenausgleich durchgehen, den wir eingerichtet haben. Daher setzen wir in diesem Beispiel die URL außer Kraft, um Skype for Business Server zu wissen, dass der ganze HTTP/S-Datenverkehr an "webint.contoso.local" und nicht an "pool.contoso.local" gehen soll, wie in der Abbildung dargestellt. Weitere Informationen zum Lastenausgleich finden Sie unter [Lastenausgleichsanforderungen für Skype for Business.](../../plan-your-deployment/network-requirements/load-balancing.md)
    
    > [!IMPORTANT]
    > Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools ist, ist die https://webint.contoso.local Basis-URL webint.contoso.local. 
  
    - Wenn Sie wie in diesem Beispiel den DNS-Lastenausgleich konfigurieren, aktivieren Sie das Kontrollkästchen **FQDN** des internen Webdienstepools außer Kraft setzen, und geben Sie in der internen Basis-URL die interne **Basis-URL**(die sich vom Pool-FQDN unterscheiden muss) ein. 
    
    > [!CAUTION]
    > Wenn Sie die internen Webdienste mit einem selbst definierten FQDN überschreiben möchten, muss jeder FQDN von jedem anderen Front-End-Pool, Director oder Directorpool eindeutig sein. **Verwenden Sie nur Standardzeichen** (einschließlich A-Z, a-z, 0-9 und Bindestriche), wenn Sie URLs oder vollqualifizierte Domänennamen definieren. Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Nicht standardmäßige Zeichen in einer URL oder einem FQDN werden häufig nicht von externen DNS- und öffentlichen Zertifizierungsstellen unterstützt (d. h. wenn die URL oder der FQDN dem Betreffnamen oder alternativen Namen im Zertifikat zugewiesen werden muss).
  
    - Geben Sie optional die externe Basis-URL in die **externe Basis-URL ein.** Geben Sie die externe Basis-URL ein, um sie von Ihrem internen Domänennamen zu unterscheiden. Ihre interne Domäne ist z. B. "contoso.local", ihr externer Domänenname ist jedoch contoso.com. Sie würden die URL mit dem contoso.com definieren, da sie aus öffentlichem DNS aufgelöst werden kann. Dies ist auch im Fall eines Reverseproxys wichtig. Der Domänenname der externen Basis-URL würde dem Domänennamen des vollqualifizierten Domänennamens des Reverseproxys entsprechen. Der HTTP-Zugriff auf den Front-End-Pool ist für Chat und Anwesenheit auf mobilen Clients erforderlich.
    
      ![Überschreiben von Webdiensten.](../../media/8f95313c-2df4-4885-adc5-9fc9ea775406.png)
  
11. Wenn Sie auf **der** Seite  "Funktionen auswählen" die Option "Konferenzen" ausgewählt haben, werden Sie aufgefordert, einen Office Web Apps-Server auszuwählen. Klicken **Sie auf "Neu",** um das Dialogfeld zu starten.
    
12. Geben Sie im Dialogfeld Neuen **Office Web Apps #A0** definieren den FQDN Ihres Office Web #A1 in das **Feld FQDN** von Office Web Apps Server ein. Wenn Sie dies tun, sollte ihre Office Web Apps-Serverermittlungs-URL automatisch in das **Office Web Apps Server-Such-URL-Feld eingegeben** werden.
    
    Wenn der Office Web Apps-Server lokal und in derselben Netzwerkzone wie Skype for Business Server installiert ist, wählen Sie nicht die Option aus, dass Office Web Apps Server in einem externen Netzwerk (d. h. **Umkreis/Internet)** bereitgestellt wird.
    
    Wenn der Office Web Apps-Server außerhalb der internen Firewall bereitgestellt wird, wählen Sie die Option Aus, dass Office Web Apps Server in einem externen Netzwerk (d. h. **Umkreis/Internet)** bereitgestellt wird.
    
13. Klicken **Sie auf "Fertig** stellen", um die Konfiguration fertig zu stellen. Wenn Sie andere Rollenserver auf der Seite "Serverrollen dieser **Front-End-Poolseite** zuordnen" definiert haben, werden separate Seiten des Assistenten für die Rollenkonfiguration geöffnet, auf denen Sie die Serverrollen konfigurieren können. In diesem Beispiel haben wir nur Konferenzen ausgewählt.
    
### <a name="configure-simple-urls"></a>Konfigurieren einfacher URLs

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den obersten Knoten von **Skype for Business Server,** und klicken Sie dann auf "Eigenschaften bearbeiten", wie in der Abbildung dargestellt.
    
     ![Klicken Sie mit der rechten Maustaste auf Skype for Business Server, und wählen Sie "Eigenschaften bearbeiten" aus.](../../media/692c18dd-8e99-4239-ae7b-5e855d866afa.png)
  
2. Wählen Sie im Bereich Einfache **URLs** entweder URLs für den Telefonzugriff aus: (Einwahl- oder Besprechungs-URLs): (Besprechungs-URLs) zum Bearbeiten, und klicken Sie dann auf  **"URL bearbeiten".** 
    
3. Aktualisieren Sie die URL auf den gewünschten Wert, und klicken Sie auf **OK**, um die bearbeitete URL zu speichern. Sie sollten die einfache URL mithilfe der externen SIP-Domäne konfigurieren, damit externe Benutzer an Besprechungen teilnehmen können, z. B. contoso.com, das extern ist, im Gegensatz zu "contoso.local", bei dem es sich um eine interne Domäne handelt. Daher sollte die SIP-Domäne von externem DNS aufgelöst werden können.
    
4. Bearbeiten Sie ggf. auch die Besprechungs-URL, indem Sie dieselben Schritte ausführen.
    
### <a name="to-define-the-optional-admin-simple-url"></a>So definieren Sie die optionale einfache URL für den administrativen Zugriff

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den **Knoten "Skype for Business Server",** und klicken Sie dann auf **"Eigenschaften bearbeiten".**
    
2. Geben Sie **im Feld "URL** für den administrativen Zugriff" die einfache URL ein, die Sie für den Administratorzugriff auf die Skype for Business Server-Systemsteuerung verwenden möchten, und klicken Sie dann auf **"OK".**
    
    > [!TIP]
    > Es wird empfohlen, eine möglichst einfache URL als Admin-URL zu verwenden. Die einfachste Option ist https://admin . _\<domain\>_ . Die Admin-URL kann entweder eine interne oder eine externe Domäne sein, z. B. contoso.local oder contoso.com, solange ein Eintrag im internen DNS aufgelöst werden kann. 
  
    > [!IMPORTANT]
    > Wenn Sie eine einfache URL nach der anfänglichen Bereitstellung ändern, müssen Sie sich der Auswirkungen auf DNS-Einträge (Domain Name System) und Zertifikate für einfache URLs bewusst sein. Wenn sich die Änderung auf die Basis einer einfachen URL ausdingt, müssen Sie auch die DNS-Einträge und -Zertifikate ändern. Wenn Sie z. B. die Basis-URL von sfb.contoso.com zu meet.contoso.com ändern, müssen Sie die DNS-Einträge und -Zertifikate so ändern, dass sie auf https://sfb.contoso.com/Meet https://meet.contoso.com meet.contoso.com. Wenn Sie die einfache URL in geändert haben, bleibt die Basis-URL von sfb.contoso.com identisch, sodass keine DNS- oder https://sfb.contoso.com/Meet https://sfb.contoso.com/Meetings Zertifikatänderungen erforderlich sind. Wenn Sie jedoch einen Namen für eine einfache URL ändern, müssen Sie das **Cmdlet "Enable-CsComputer"** auf jedem Director- und Front-End-Server ausführen, um die Änderung zu registrieren.
  
### <a name="publish-and-verify-the-topology"></a>Veröffentlichen und Überprüfen der Topologie

1. Vergewissern Sie sich, dass alle einfachen URLs richtig konfiguriert wurden.
    
2. Vergewissern Sie sich SQL Server der serverbasierte Server online ist und für den Computer verfügbar ist, auf dem der Topologie-Generator installiert ist, einschließlich aller erforderlichen Firewallregeln.
    
3. Vergewissern Sie sich, dass die Dateifreigabe verfügbar ist und dass die entsprechenden Berechtigungen definiert sind.
    
4. Stellen Sie sicher, dass die richtigen Serverrollen zur Erfüllung der Bereitstellungsanforderungen in der Topologie definiert wurden.
    
5. Stellen Sie sicher, dass die Server in Active Directory Domain Services (AD DS) vorhanden sind. Dies geschieht automatisch, wenn Sie die Server der Domäne hinzufügen.
    
    Wenn Sie die Topologie überprüft haben und keine Überprüfungsfehler aufgetreten sind, können Sie die Topologie veröffentlichen. Wenn Überprüfungsfehler auftreten, müssen Sie diese korrigieren, bevor Sie die Topologie veröffentlichen können.
    
6. Klicken Sie mit der rechten Maustaste auf den **Knoten "Skype for Business Server",** und klicken Sie dann **auf "Topologie veröffentlichen".**
    
7. Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
8. Wählen Sie **auf der Seite "Zentralen Verwaltungsserver** auswählen" einen Front-End-Pool aus, wie in der Abbildung dargestellt.
    
    > [!NOTE]
    > Sie können auf **"Erweitert"** klicken, um Speicherorte für Datenbankdateien zu konfigurieren.
  
     ![Wählen Sie den zentralen Verwaltungsspeicherserver aus.](../../media/764478b5-8480-42c5-854f-649bb121cd94.png)
  
9. Wählen Sie **auf der** Seite Datenbanken auswählen die Datenbanken aus, die Sie veröffentlichen möchten.
    
    > [!NOTE]
    > Wenn Sie nicht über die entsprechenden Rechte zum Erstellen der Datenbanken verfügen, können Sie die Kontrollkästchen neben diesen Datenbanken löschen, und ein Benutzer mit den entsprechenden Rechten kann die Datenbanken später erstellen. Weitere Informationen zu den Anforderungen finden Sie unter ["Serveranforderungen für Skype for Business Server".](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 
  
10. Klicken Sie optional auf **Erweitert**. Mithilfe der optionen SQL Server erweiterte Datendatei können Sie zwischen den folgenden Optionen auswählen: 
    
    - **Speicherort der Datenbankdatei** automatisch bestimmen – Diese Option bestimmt die beste Betriebsleistung basierend auf der Datenträgerkonfiguration auf dem SQL Server-basierten Server, indem die Protokolldateien und Datendateien am besten verteilt werden.
    
    - **Standardeinstellungen SQL Server** Instanz verwenden– Mit dieser Option werden Protokoll- und Datendateien mithilfe der Instanzeinstellungen auf dem SQL Server serverbasierten Server gespeichert. Diese Option macht keinen Gebrauch von der Funktion des SQL Server-basierten Servers zum Ermitteln der optimalen Speicherorte für Protokolle und Daten. Der SQL Server-Administrator verschiebt die Protokoll- und Datendateien in der Regel an Speicherorte, die für den SQL Server-basierten Server geeignet sind und den Verwaltungsverfahren für die Organisation entsprechen.
    
    Klicken Sie auf **OK** und dann auf **Weiter**. 
    
11. Klicken Sie optional auf **"Erweitert".** Mithilfe der optionen SQL Server erweiterte Datendatei können Sie zwischen den folgenden Optionen auswählen: 
    
    - **Speicherort der Datenbankdatei** automatisch bestimmen – Diese Option bestimmt die beste Betriebsleistung basierend auf der Datenträgerkonfiguration auf dem SQL Server-basierten Server, indem die Protokolldateien und Datendateien am besten verteilt werden.
    
    - **Standardeinstellungen SQL Server** Instanz verwenden– Mit dieser Option werden Protokoll- und Datendateien mithilfe der Instanzeinstellungen auf dem SQL Server serverbasierten Server gespeichert. Diese Option macht keinen Gebrauch von der Funktion des SQL Server-basierten Servers zum Ermitteln der optimalen Speicherorte für Protokolle und Daten. Der SQL Server-Administrator verschiebt die Protokoll- und Datendateien in der Regel an Speicherorte, die für den SQL Server-basierten Server geeignet sind und den Verwaltungsverfahren für die Organisation entsprechen.
    
    Klicken Sie auf **OK**.
    
12. Klicken Sie auf **Weiter**, um die Veröffentlichung abzuschließen.
    
    > [!NOTE]
    > Ein häufiger Fehler bei diesem Schritt ist, dass die SQL Server nicht erstellt werden können. Wenn der Prozess nicht abgeschlossen werden kann, wird ein Fehler bereitgestellt, wie in der Abbildung dargestellt. Die wahrscheinlichste Ursache ist, dass der Benutzer, der versucht, die Datenbank zu erstellen, nicht über die entsprechenden Berechtigungen verfügt oder das SQL Server-System aufgrund eines Firewall- oder anderen Netzwerkproblems nicht kontaktiert werden kann. 
  
     ![Fehler beim Erstellen des zentralen Verwaltungsspeichers.](../../media/558bd2e4-2721-422d-9986-df86f642e6a1.png)
  
13. Nach Abschluss des Veröffentlichungsprozesses wird ein Link zum Öffnen einer Liste der nächsten Schritte angezeigt. Klicken **Sie hier, um die To-Do-Liste** zum Anzeigen der nächsten Schritte zu öffnen, und klicken Sie dann auf **Fertig stellen**. 
    
    Die Meldung "Mit Warnungen abgeschlossen" für die Datenbankerstellung bedeutet nicht, dass ein Fehler aufgetreten ist. Der Installationsprozess muss die Einstellungen in SQL Server, damit Skype for Business Server ordnungsgemäß funktioniert. Wenn eine Einstellung in SQL Server geändert wird, wird sie als Warnung protokolliert, damit SQL Server genau wissen können, was der Installationsprozess abgeschlossen hat. Wenn eine Warnung angezeigt wird, können Sie den  Datensatz auswählen und dann auf "Protokolle anzeigen" klicken, um die Details der Warnung anzuzeigen.
    
    Nachdem die Topologie erfolgreich veröffentlicht wurde, können Sie mit der Installation eines lokalen Replikats des zentralen Verwaltungsspeichers auf jedem Server beginnen, auf dem Skype for Business Server in Ihrer Topologie ausgeführt wird. Es wird empfohlen, mit dem ersten Front-End-Pool zu beginnen. 
    

