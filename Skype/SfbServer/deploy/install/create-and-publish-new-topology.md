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
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine neue Topologie erstellen, veröffentlichen und überprüfen, bevor Sie Skype for Business Server installieren. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation Center herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: cc5647211732189ba172d75a64e12d93e988c4063827f132b476e8ca96ee2808
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331877"
---
# <a name="create-and-publish-new-topology-in-skype-for-business-server"></a>Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie eine neue Topologie erstellen, veröffentlichen und überprüfen, bevor Sie Skype for Business Server installieren. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation Center herunter: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .
  
Bevor Sie das Skype for Business Server System auf jedem Server in der Topologie installieren können, müssen Sie eine Topologie erstellen und veröffentlichen. Wenn Sie eine Topologie veröffentlichen, laden Sie die Topologieinformationen in die zentrale Verwaltungsdatenbank Store. Wenn es sich um einen Enterprise Edition Pool handelt, erstellen Sie die zentrale Verwaltungsdatenbank Store Datenbank, wenn Sie zum ersten Mal eine neue Topologie veröffentlichen. Wenn dies Standard Edition ist, müssen Sie den Prozess "Erste Standard Edition Server vorbereiten" aus dem Bereitstellungs-Assistenten ausführen, bevor Sie eine Topologie veröffentlichen. Dadurch wird die Standard Edition vorbereitet, indem eine SQL Server Express Edition-Instanz installiert und die zentrale Verwaltungs Store erstellt wird. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm beschrieben. Das Erstellen und Veröffentlichen einer neuen Topologie wird in Schritt 6 von 8 beschrieben.
  
![Übersichtsdiagramm](../../media/c5c09ba2-c98b-4194-9857-7c3087c5560e.png)
  
## <a name="create-and-publish-new-topology"></a>Erstellen und Veröffentlichen einer neuen Topologie

Sie können Skype for Business Server Topologie-Generator zum Entwerfen, Definieren, Konfigurieren und Veröffentlichen von Topologien verwenden. Dieses Tool wurde installiert, als Sie die Verwaltungstools weiter oben in diesem Artikel installiert haben. Es gibt viele verschiedene Optionen, die Sie beim Erstellen einer Topologie treffen können. In diesem Verfahren erstellen Sie eine grundlegende Topologie mit Konferenzen.
  
> [!IMPORTANT]
> Skype for Business Server erfordert SQL Server für den Betrieb. Die primären Datenbanken werden als zentrale Verwaltungs Store bezeichnet. Wenn Sie Enterprise Edition bereitstellen, werden diese Datenbanken erstellt, wenn Sie die Topologie mithilfe der folgenden Schritte veröffentlichen. In diesem Fall werden Sie vom Topologie-Generator nach den Verbindungsinformationen zu einer SQL Server Installation gefragt. Wenn Sie planen, Standard Edition bereitzustellen, müssen Sie SQL Server Express Edition installieren, bevor Sie die neue Topologie definieren und veröffentlichen. Um SQL Server Express Edition zu installieren, sollten Sie den Bereitstellungs-Assistenten auf dem Server öffnen, der als Front-End fungiert, und dann "Vorbereitung zuerst Standard Edition Server" ausführen. Wenn Sie auf "Erste Standard Edition Server vorbereiten" klicken, installiert der Bereitstellungs-Assistent automatisch SQL Server Express Edition und erstellt die datenbanken für die zentrale Verwaltung Store. 
  
### <a name="create-a-new-topology"></a>Erstellen einer neuen Topologie

1. Melden Sie sich als Standardbenutzer mit Zugriff auf den Topologie-Generator an.
    
2. Öffnen Sie Skype for Business Server Topologie-Generator.
    
3. Wählen Sie **"Neue Topologie"** aus, und klicken Sie auf **"OK".**
    
4. Wählen Sie einen Speicherort und einen Dateinamen für die Topologiekonfigurationsdatei aus.
    
    > [!NOTE]
    > Die Topologiekonfiguration wird als TOPOLOGIE-Generator-XML-Datei (.tbxml) gespeichert. Wenn Sie eine Topologie veröffentlichen, übertragen Sie die Konfigurationsinformationen aus der Datei an die SQL Server Datenbank. Wenn Sie den Topologie-Generator in Zukunft öffnen, können Sie die vorhandene Konfiguration aus SQL Server direkt im Topologie-Generator herunterladen und sie entweder wieder in SQL Server veröffentlichen oder als Topologie-Generator-Konfigurationsdatei speichern. 
  
5. Geben Sie auf **dem Bildschirm "Primäre Domäne definieren"** die **primäre SIP-Domäne** ein, und klicken Sie auf **"Weiter".** In diesem Beispiel verwenden wir **"contoso.local",** wie in der Abbildung dargestellt.
    
     ![Definieren Sie die primäre SIP-Domäne.](../../media/353e6b38-485f-4042-8585-aefa6c74b554.png)
  
6. Fügen Sie alle zusätzlichen unterstützten SIP-Domänen hinzu, und klicken Sie dann auf **"Weiter".**
    
7. Geben Sie einen **Namen** und eine **Beschreibung** für die erste Website (Speicherort) ein, und klicken Sie dann auf **"Weiter",** wie in der Abbildung dargestellt.
    
     ![Definieren Sie die erste Website (Speicherort).](../../media/d8b6c54a-2011-4efb-97fb-a4de0f11303c.png)
  
8. Geben Sie den **Code für Ort,** **Bundesland/Kanton** und **Land/Region** für die Website ein, und klicken Sie dann auf **"Weiter".**
    
9. Klicken Sie auf **"Fertig stellen",** um den Vorgang zum Definieren einer neuen Topologie abzuschließen. Der Assistent für das neue Front-End wird automatisch gestartet.
    
### <a name="define-a-front-end-pool-or-standard-edition-server"></a>Definieren eines Front-End-Pools oder Standard Edition Servers

1. Überprüfen Sie die Voraussetzungen des Assistenten, und klicken Sie dann auf **"Weiter".**
    
2. Geben Sie den vollqualifizierten Domänennamen (FQDN) des Pools ein, und wählen Sie **entweder Enterprise Edition Front-End-Pool** oder **Standard Edition Server** aus, und klicken Sie dann auf **"Weiter",** wie in der Abbildung dargestellt.
    
    > [!TIP]
    > Skype for Business Server Enterprise Edition können mehrere Server umfassen, die zusammenarbeiten, um die Front-End-Rolle bereitzustellen. Wenn mehrere Server verwendet werden, um die Rolle zu erfüllen, wird dies als Pool bezeichnet. Daher werden mehrere Server, die zusammenarbeiten, um die Front-End-Rolle bereitzustellen, auch als Front-End-Pool bezeichnet. Skype for Business Server Standard Edition kann nur einen einzelnen Server enthalten, um die Front-End-Rolle bereitzustellen. Es ist üblich, auf den Front-End-Pool zu verweisen, auch wenn nur ein einzelner Server die Rolle bereitstellt. 
  
     ![Definieren Sie den Front-End-Pool.](../../media/c1447557-261e-4260-a362-ab8d19070eb9.png)
  
3. Geben Sie die vollqualifizierten Domänennamen (Fully Qualified Domain Names, FQDNs) aller Computer im Pool ein, und klicken Sie dann auf **"Weiter",** wie in der Abbildung dargestellt.
    
     ![Definieren Sie die Computer im Pool.](../../media/1106b4f3-8745-485b-b495-f885a5dfefda.png)
  
4. Wählen Sie die Features aus, die in dieser Topologie enthalten sein werden, und klicken Sie dann auf **"Weiter",** wie in der Abbildung dargestellt.
    
    > [!NOTE]
    > Skype for Business Server enthält viele erweiterte Features. Lesen Sie die Planungs- und Bereitstellungsdokumentation für jedes feature, das Sie verwenden möchten. 
  
     ![Wählen Sie Features für die Bereitstellung aus.](../../media/77257588-d0e1-4517-a12a-869ffe009353.png)
  
5. Auf der Seite **"Gemeinsam zugeordnete Serverrollen auswählen"** können Sie den Vermittlungsserver auf dem Front-End-Server oder als eigenständigen Server bereitstellen.
    
    Wenn Sie beabsichtigen, den Vermittlungsserver im Enterprise Edition Front-End-Pool zu verbinden, stellen Sie sicher, dass das Kontrollkästchen aktiviert ist. Die Serverrolle wird auf den Poolservern bereitgestellt. Wenn Sie beabsichtigen, den Vermittlungsserver als eigenständigen Server bereitzustellen, deaktivieren Sie das entsprechende Kontrollkästchen. Sie stellen den Vermittlungsserver in einem separaten Bereitstellungsschritt bereit, nachdem Sie den Front-End-Server vollständig bereitgestellt haben. Ausführliche Informationen zur Planung einer Kollokation finden Sie unter [Topologiegrundlagen für Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md).
    
6. Mithilfe der Seite **"Serverrollen diesem Front-End-Pool zuordnen"** können Sie Serverrollen definieren und dem Front-End-Pool zuordnen. Die folgende Rolle ist verfügbar:
    
    **Aktivieren eines Edgepools** Definiert und ordnet einen einzelnen Edgeserver oder einen Pool von Edgeservern zu. Ein Edgeserver erleichtert die Kommunikation und Zusammenarbeit zwischen Benutzern innerhalb der Organisation und Personen außerhalb der Organisation, einschließlich Verbundbenutzern.
    
    Es gibt zwei mögliche Szenarien, mit denen Sie die Serverrollen bereitstellen und zuordnen können.
    
    In Szenario 1 definieren Sie eine neue Topologie für eine Neuinstallation. Sie können die Installation auf eine der beiden folgenden Arten behandeln:
    
   - Lassen Sie das Kontrollkästchen deaktiviert, und definieren Sie die Topologie. Nachdem Sie die Front-End- und Back-End-Serverrollen veröffentlicht, konfiguriert und getestet haben, können Sie den Topologie-Generator erneut ausführen, um die Rollenserver der Topologie hinzuzufügen. Mit dieser Strategie können Sie den Front-End-Pool und den Server, auf dem SQL Server ausgeführt wird, ohne zusätzliche Komplikationen durch zusätzliche Rollen testen. Nachdem Sie die ersten Tests abgeschlossen haben, können Sie den Topologie-Generator erneut ausführen, um die Rollen auszuwählen, die Sie bereitstellen müssen.
    
   - Wählen Sie die Rollen aus, die installiert werden müssen, und richten Sie anschließend die Hardware für die ausgewählten Rollen ein.
    
     Für Szenario 2 verfügen Sie über eine vorhandene Bereitstellung, und Ihre Infrastruktur ist bereit für neue Rollen, oder Sie müssen vorhandene Rollen einem neuen Front-End-Server zuordnen.
    
   - In diesem Fall wählen Sie die Rollen aus, die Sie bereitstellen oder dem neuen Front-End-Server zuordnen möchten. In beiden Fällen fahren Sie mit der Definition der Rollen fort, richten gegebenenfalls erforderliche Hardware ein und führen die Installation aus.
    
7. Als Nächstes definieren Sie den SQL Server Speicher, der mit der Topologie verwendet wird. In diesem Beispiel wird die Standardinstanz verwendet. Weitere Informationen zu SQL Server Features, z. B. hohe Verfügbarkeit, finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
    
   - Zum Verwenden eines vorhandenen SQL Server-Speichers, der bereits in Ihrer Topologie definiert wurde, wählen Sie eine Instanz unter **SQL-Speicher** aus.
    
   - Klicken Sie zum Definieren einer neuen SQL Server Instanz zum Speichern von Poolinformationen auf **"Neu",** und geben Sie dann den **FQDN SQL Server** im Dialogfeld **"Neue SQL Store definieren"** an.
    
   - Zum Angeben des Namens einer SQL Server-Instanz wählen Sie **Benannte Instanz**, und geben Sie anschließend den Namen der Instanz an.
    
   - Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden.
    
   - Um SQL Spiegelung zu verwenden, wählen **Sie "SQL Spiegelung aktivieren"** und dann eine vorhandene Instanz aus, oder erstellen Sie eine neue Instanz.

     > [!NOTE]
     > SQL Spiegelung ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die Methoden AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen (FCI) und SQL Failoverclustering werden mit Skype for Business Server 2019 bevorzugt.
    
     In diesem Beispiel geben wir den **SQL Server FQDN** ein, konfigurieren alle relevanten Einstellungen für hohe Verfügbarkeit, und klicken dann auf **"OK",** wie in der Abbildung dargestellt.
    
     ![Erstellen Sie einen SQL Server Speicher.](../../media/12822cf9-8608-43c0-94ce-2ca8b3a0ffd5.png)
  
8. Entscheiden Sie, ob Sie SQL Server Speicherspiegelung oder SQL Server Spiegelungszeugen aktivieren möchten, und klicken Sie dann auf **"Weiter".**
    
9. Definieren Sie die Dateifreigabe, die Sie verwenden möchten.
    
   - Zum Verwenden einer Dateifreigabe, die bereits in Ihrer Topologie definiert wurde, wählen Sie **Zuvor definierte Dateifreigabe verwenden**.
    
   - Zum Definieren einer neuen Dateifreigabe wählen Sie **Neue Dateifreigabe definieren**, geben Sie im Feld **Dateiserver-FQDN** den vollqualifizierten Domänennamen des vorhandenen Dateiservers ein, auf dem sich die Dateifreigabe befinden soll, und geben Sie anschließend einen Namen für die Dateifreigabe in das Feld **Dateifreigabe** ein.
    
     In diesem Beispiel klicken wir auf **"Neuen Dateispeicher definieren",** geben den **Dateiserver-FQDN** und die **Dateifreigabe** ein und klicken dann auf **"Weiter".**
    
     > [!NOTE]
     > Die Dateifreigabe für Skype for Business Server kann verbunden werden, wird jedoch aus Leistungsgründen nicht empfohlen. Beachten Sie, dass sich die Dateifreigabe in diesem Beispiel auf einem einzelnen dedizierten Server befindet, der als Dateifreigabe fungiert. Es werden jedoch andere robustere Dateifreigabesysteme empfohlen, z. B. DFS mit Windows Server 2012 R2. Ausführliche Informationen zu unterstützten Dateifreigabesystemen finden Sie unter [Anforderungen für Ihre Skype for Business Umgebung.](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) Weitere Informationen zum Erstellen der Dateifreigabe finden Sie unter [Erstellen einer Dateifreigabe in Skype for Business Server](create-a-file-share.md). Sie können die Dateifreigabe definieren, ohne dass die Dateifreigabe erstellt wurde. Sie müssen die Dateifreigabe am definierten Speicherort erstellen, bevor Sie die Topologie veröffentlichen. 
  
10. Auf der Seite "Webdienst-URL angeben" müssen Sie entscheiden, ob Sie die basis-URL des internen Webdienstpools überschreiben müssen. Der Grund für diese Außerkraftsetzung liegt im Lastenausgleich. Einfacher SIP-Datenverkehr kann über einen einfachen DNS-Lastenausgleich geladen werden. Der HTTP/S-Webdienst-Netzwerkdatenverkehr muss jedoch eine unterstützte Hardware- oder Software-Lastenausgleichslösung verwenden. Unterstützte Lastenausgleichsmodule finden Sie unter [Infrastruktur für Skype for Business.](../../../SfbPartnerCertification/certification/infra-gateways.md) In diesem Beispiel haben wir den DNS-Lastenausgleich für SIP-Datenverkehr und eine unterstützte Lösung für den Softwarelastenausgleich verwendet. Da der Datenverkehr auf diese Weise geteilt wird, müssen wir den FQDN des internen Webdienstpools überschreiben. Wenn wir über ein Top-Line-Lastenausgleichsmodul verfügen und den gesamten Datenverkehr darüber senden würden, anstatt DNS-Lastenausgleich für SIP-Datenverkehr zu verwenden, müssten wir die Webdienst-URL nicht überschreiben. 
    
    Im DNS-Abschnitt dieses Themas haben wir einen A-Eintrag für webint.contoso.local erstellt. Dies ist die URL, die wir für den HTTP/S-Datenverkehr der Webdienste verwenden, und sie muss den von uns eingerichteten unterstützten Softwarelastenausgleich durchlaufen. Daher überschreiben wir in diesem Beispiel die URL, um Skype for Business Server mitzuteilen, dass der gesamte HTTP/S-Datenverkehr zu "webint.contoso.local" anstelle von "pool.contoso.local" (siehe Abbildung) gehen soll. Weitere Informationen zum Lastenausgleich finden Sie unter [Lastenausgleichsanforderungen für Skype for Business.](../../plan-your-deployment/network-requirements/load-balancing.md)
    
    > [!IMPORTANT]
    > Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools https://webint.contoso.local lautet, lautet die Basis-URL "webint.contoso.local". 
  
    - Wenn Sie den DNS-Lastenausgleich konfigurieren, aktivieren Sie wie in diesem Beispiel das Kontrollkästchen **"Internen Webdienstpool-FQDN überschreiben",** und geben Sie die interne Basis-URL (die sich vom Pool-FQDN unterscheiden muss) in die **interne Basis-URL** ein. 
    
    > [!CAUTION]
    > Wenn Sie die internen Webdienste mit einem selbst definierten FQDN überschreiben möchten, muss jeder FQDN für jeden anderen Front-End-Pool, Director oder Director-Pool eindeutig sein. **Verwenden Sie nur Standardzeichen** (einschließlich A-Z, a-z, 0-9 und Bindestriche), wenn Sie URLs oder vollqualifizierte Domänennamen definieren. Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Nicht standardmäßige Zeichen in einer URL oder einem FQDN werden häufig von externen DNS- und öffentlichen Zertifizierungsstellen (Public Certification Authorities, CAs) nicht unterstützt (d. b. wenn die URL oder der FQDN dem Antragstellernamen oder alternativen Antragstellernamen im Zertifikat zugewiesen werden muss).
  
    - Geben Sie optional die externe Basis-URL in die **externe Basis-URL** ein. Sie geben die externe Basis-URL ein, um sie von Ihrem internen Domänennamen zu unterscheiden. Ihre interne Domäne lautet z. B. "contoso.local", ihr externer Domänenname ist jedoch contoso.com. Sie würden die URL mithilfe des contoso.com Domänennamens definieren, da er aus öffentlichem DNS aufgelöst werden kann. Dies ist auch im Fall eines Reverseproxys wichtig. Der Domänenname der externen Basis-URL würde dem Domänennamen des vollqualifizierten Domänennamens des Reverseproxys entsprechen. HTTP-Zugriff auf den Front-End-Pool ist für Chatnachrichten und Anwesenheitsinformationen auf mobilen Clients erforderlich.
    
      ![Webdienste außer Kraft setzen.](../../media/8f95313c-2df4-4885-adc5-9fc9ea775406.png)
  
11. Wenn Sie auf der Seite **"Features auswählen"** die Option **"Konferenzen"** ausgewählt haben, werden Sie aufgefordert, einen Office Web Apps-Server auszuwählen. Klicken Sie auf **Neu,** um das Dialogfeld zu starten.
    
12. Geben Sie im Dialogfeld **"Neuen Office Web Apps-Server definieren"** den FQDN ihres Office Web Apps-Servers in das **Feld Office Web Apps Server-FQDN** ein. Wenn Sie dies tun, sollte ihre Office Web Apps-Serverermittlungs-URL automatisch in das **Feld Office Web Apps-Serverermittlungs-URL** eingegeben werden.
    
    Wenn der Office Web Apps-Server lokal installiert ist und sich in derselben Netzwerkzone wie Skype for Business Server befindet, wählen Sie nicht die Option **aus, Office Web Apps-Server in einem externen Netzwerk (d. h. Perimeter/Internet) bereitgestellt wird.**
    
    Wenn der Office Web Apps-Server außerhalb Ihrer internen Firewall bereitgestellt wird, wählen Sie die Option **aus, Office Web Apps-Server in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt wird.**
    
13. Klicken Sie auf **Fertig stellen,** um die Konfiguration abzuschließen. Wenn Sie andere Rollenserver auf der Seite **"Serverrollen zuordnen" mit dieser Front-End-Poolseite** definiert haben, werden separate Assistentenseiten für die Rollenkonfiguration geöffnet, auf denen Sie die Serverrollen konfigurieren können. In diesem Beispiel haben wir nur Konferenzen ausgewählt.
    
### <a name="configure-simple-urls"></a>Konfigurieren einfacher URLs

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den **Skype for Business Server** oberen Knoten, und klicken Sie dann auf **"Eigenschaften bearbeiten",** wie in der Abbildung dargestellt.
    
     ![Klicken Sie mit der rechten Maustaste auf Skype for Business Server, und wählen Sie "Eigenschaften bearbeiten" aus.](../../media/692c18dd-8e99-4239-ae7b-5e855d866afa.png)
  
2. Wählen Sie im Bereich **einfache URLs** entweder **Telefon UrLs zugreifen:** (Einwahl) oder **Besprechungs-URLs:** (Besprechung), um sie zu bearbeiten, und klicken Sie dann auf **"URL bearbeiten".**
    
3. Aktualisieren Sie die URL auf den gewünschten Wert, und klicken Sie auf **OK**, um die bearbeitete URL zu speichern. Sie sollten die einfache URL mithilfe der externen SIP-Domäne konfigurieren, damit externe Benutzer an Besprechungen teilnehmen können, z. B. contoso.com, die extern ist, im Gegensatz zu contoso.local, einer internen Domäne. Daher sollte die SIP-Domäne durch externes DNS aufgelöst werden können.
    
4. Bearbeiten Sie ggf. auch die Besprechungs-URL, indem Sie dieselben Schritte ausführen.
    
### <a name="to-define-the-optional-admin-simple-url"></a>So definieren Sie die optionale einfache URL für den administrativen Zugriff

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den **Knoten Skype for Business Server,** und klicken Sie dann auf **Eigenschaften bearbeiten.**
    
2. Geben Sie im Feld ADMINISTRATIVE **ZUGRIFFS-URL** die einfache URL ein, die Sie für den Administratorzugriff auf Skype for Business Server Systemsteuerung wünschen, und klicken Sie dann auf **OK.**
    
    > [!TIP]
    > Es wird empfohlen, eine möglichst einfache URL als Admin-URL zu verwenden. Die einfachste Option ist https://admin . _\<domain\>_ . Die Admin-URL kann entweder eine interne oder externe Domäne sein, z. B. contoso.local oder contoso.com, solange beide Einträge im internen DNS aufgelöst werden können. 
  
    > [!IMPORTANT]
    > Wenn Sie eine einfache URL nach der anfänglichen Bereitstellung ändern, müssen Sie sich der Auswirkungen auf DNS-Einträge (Domain Name System) und Zertifikate für einfache URLs bewusst sein. Wenn sich die Änderung auf die Basis einer einfachen URL auswirkt, müssen Sie auch die DNS-Einträge und -Zertifikate ändern. Wenn Sie beispielsweise https://sfb.contoso.com/Meet https://meet.contoso.com die Basis-URL von sfb.contoso.com in meet.contoso.com ändern, müssen Sie die DNS-Einträge und -Zertifikate so ändern, dass sie auf meet.contoso.com verweisen. Wenn Sie die einfache URL von in geändert https://sfb.contoso.com/Meet https://sfb.contoso.com/Meetings haben, bleibt die Basis-URL von sfb.contoso.com unverändert, sodass keine DNS- oder Zertifikatsänderungen erforderlich sind. Wenn Sie jedoch einen einfachen URL-Namen ändern, müssen Sie das Cmdlet **"Enable-CsComputer"** auf jedem Director- und Front-End-Server ausführen, um die Änderung zu registrieren.
  
### <a name="publish-and-verify-the-topology"></a>Veröffentlichen und Überprüfen der Topologie

1. Vergewissern Sie sich, dass alle einfachen URLs richtig konfiguriert wurden.
    
2. Vergewissern Sie sich, dass der SQL Server-basierte Server online ist und auf dem Computer verfügbar ist, auf dem der Topologie-Generator installiert ist, einschließlich aller erforderlichen Firewallregeln.
    
3. Vergewissern Sie sich, dass die Dateifreigabe verfügbar ist und dass die richtigen Berechtigungen definiert sind.
    
4. Stellen Sie sicher, dass die richtigen Serverrollen zur Erfüllung der Bereitstellungsanforderungen in der Topologie definiert wurden.
    
5. Stellen Sie sicher, dass die Server in Active Directory Domain Services (AD DS) vorhanden sind. Dies geschieht automatisch, wenn Sie die Server der Domäne hinzufügen.
    
    Wenn Sie die Topologie überprüft haben und keine Überprüfungsfehler aufgetreten sind, können Sie die Topologie veröffentlichen. Wenn Validierungsfehler vorhanden sind, müssen Sie diese korrigieren, bevor Sie die Topologie veröffentlichen können.
    
6. Klicken Sie mit der rechten Maustaste auf den **Knoten Skype for Business Server,** und klicken Sie dann auf **"Topologie veröffentlichen".**
    
7. Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
8. Wählen Sie auf der Seite **"Zentralen Verwaltungsserver auswählen"** einen Front-End-Pool aus, wie in der Abbildung dargestellt.
    
    > [!NOTE]
    > Sie können auf **"Erweitert"** klicken, um Speicherorte für Datenbankdateien zu konfigurieren.
  
     ![Wählen Sie "Zentrale Verwaltung Store Server" aus.](../../media/764478b5-8480-42c5-854f-649bb121cd94.png)
  
9. Wählen Sie auf der Seite **"Datenbanken auswählen"** die Datenbanken aus, die Sie veröffentlichen möchten.
    
    > [!NOTE]
    > Wenn Sie nicht über die entsprechenden Rechte zum Erstellen der Datenbanken verfügen, können Sie die Kontrollkästchen neben diesen Datenbanken deaktivieren, und eine Person mit den entsprechenden Rechten kann die Datenbanken später erstellen. Ausführliche Informationen zu den Anforderungen finden Sie unter [Serveranforderungen für Skype for Business Server.](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 
  
10. Klicken Sie optional auf **Erweitert**. Mithilfe von Erweiterten SQL Server Optionen für die Platzierung von Datendateien können Sie zwischen den folgenden Optionen auswählen: 
    
    - **Automatisches Bestimmen** des Speicherorts von Datenbankdateien – Diese Option bestimmt die beste Betriebsleistung basierend auf der Datenträgerkonfiguration auf Ihrem SQL Server-basierten Server, indem die Protokoll- und Datendateien an den besten Speicherort verteilt werden.
    
    - **Verwenden Sie SQL Server Instanzstandardeinstellungen.** Mit dieser Option werden Protokoll- und Datendateien mithilfe der Instanzeinstellungen auf dem SQL Server-basierten Server abgelegt. Diese Option macht keinen Gebrauch von der Funktion des SQL Server-basierten Servers zum Ermitteln der optimalen Speicherorte für Protokolle und Daten. Der SQL Server-Administrator verschiebt die Protokoll- und Datendateien in der Regel an Speicherorte, die für den SQL Server-basierten Server geeignet sind und den Verwaltungsverfahren für die Organisation entsprechen.
    
    Klicken Sie auf **OK** und dann auf **Weiter**. 
    
11. Klicken Sie optional auf **"Erweitert".** Mithilfe von Erweiterten SQL Server Optionen für die Platzierung von Datendateien können Sie zwischen den folgenden Optionen auswählen: 
    
    - **Automatisches Bestimmen** des Speicherorts von Datenbankdateien – Diese Option bestimmt die beste Betriebsleistung basierend auf der Datenträgerkonfiguration auf Ihrem SQL Server-basierten Server, indem die Protokoll- und Datendateien an den besten Speicherort verteilt werden.
    
    - **Verwenden Sie SQL Server Instanzstandardeinstellungen.** Mit dieser Option werden Protokoll- und Datendateien mithilfe der Instanzeinstellungen auf dem SQL Server-basierten Server abgelegt. Diese Option macht keinen Gebrauch von der Funktion des SQL Server-basierten Servers zum Ermitteln der optimalen Speicherorte für Protokolle und Daten. Der SQL Server-Administrator verschiebt die Protokoll- und Datendateien in der Regel an Speicherorte, die für den SQL Server-basierten Server geeignet sind und den Verwaltungsverfahren für die Organisation entsprechen.
    
    Klicken Sie auf **OK**.
    
12. Klicken Sie auf **Weiter**, um die Veröffentlichung abzuschließen.
    
    > [!NOTE]
    > Ein häufiger Fehler bei diesem Schritt ist, dass die SQL Server Datenbanken nicht erstellt werden können. Wenn der Prozess nicht abgeschlossen werden kann, wird ein Fehler angegeben, wie in der Abbildung dargestellt. Die wahrscheinlichste Ursache ist, dass der Benutzer, der versucht, die Datenbank zu erstellen, nicht über die entsprechenden Berechtigungen verfügt oder das SQL Server System aufgrund eines Firewall- oder anderen Netzwerkproblems nicht kontaktiert werden kann. 
  
     ![Fehler beim Erstellen des zentralen Verwaltungsspeichers.](../../media/558bd2e4-2721-422d-9986-df86f642e6a1.png)
  
13. Nach Abschluss des Veröffentlichungsprozesses wird ihnen ein Link zum Öffnen einer Liste der nächsten Schritte angezeigt. Klicken **Sie hier, um die Aufgabenliste zu öffnen,** um die nächsten Schritte anzuzeigen, und klicken Sie dann auf **Fertig stellen**. 
    
    Die Meldung "Mit Warnungen abgeschlossen" für die Datenbankerstellung bedeutet nicht, dass ein Fehler aufgetreten ist. Der Installationsvorgang muss die Einstellungen in SQL Server ändern, damit Skype for Business Server ordnungsgemäß funktioniert. Wenn eine Einstellung in SQL Server geändert wird, wird sie als Warnung protokolliert, damit SQL Server Administratoren genau verstehen können, was der Installationsvorgang abgeschlossen hat. Wenn Sie eine Warnung erhalten, können Sie den Datensatz auswählen und dann auf **"Protokolle anzeigen"** klicken, um die Details der Warnung anzuzeigen.
    
    Nachdem die Topologie erfolgreich veröffentlicht wurde, können Sie mit der Installation eines lokalen Replikats des zentralen Verwaltungsspeichers auf jedem Server beginnen, auf dem Skype for Business Server in Ihrer Topologie ausgeführt wird. Es wird empfohlen, mit dem ersten Front-End-Pool zu beginnen. 
