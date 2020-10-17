---
title: 'Lync Server 2013: Erstellen des anfänglichen Topologie-Designs'
description: 'Lync Server 2013: Erstellen des anfänglichen Topologie-Designs.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c91bfe68a1de4a1f9862948edd708b8efa6a5c6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551091"
---
# <a name="create-the-initial-topology-design-for-lync-server-2013"></a>Erstellen des anfänglichen Topologie Designs für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Nachdem Sie die Installation des lync Server 2013 Planungstools abgeschlossen haben, können Sie das Planungstool starten und mit dem Entwerfen der vorgeschlagenen lync Server 2013 Infrastruktur beginnen.

<div>


> [!NOTE]  
> Das Planungstool ist ein Assistenten gesteuertes Tool mit detaillierten Anleitungen, um den Entscheidungsfindungsprozess beim Entwerfen Ihrer Websites und der Topologie zu informieren. Dieses Thema ist nicht als vollständiger Leitfaden gedacht, sondern dient lediglich dazu, Ihnen den Einstieg in die Verwendung des Planungstools in ihren Entwurfs Sitzungen zu erleichtern.



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>So beginnen Sie mit dem Planungs Tool und erstellen den anfänglichen Entwurf

1.  Starten des lync Server 2013, Planungstools: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **Planungstool**.

2.  Nachdem das Planungstool gestartet wurde, wird die Seite **Willkommen beim Planungstool für Microsoft lync Server 2013** angezeigt. Wählen Sie eine der folgenden Optionen aus, um mit Ihrem Entwurf zu beginnen:
    
      - **Option 1: Erste Schritte**     Wenn **Sie auf erste Schritte** klicken, wird eine bestimmte Reihe von Interview Fragen mit relevanten Auswahlmöglichkeiten zur Definition der Kriterien gestellt. Nachdem Sie den Abschnitt erste **Schritte** mit dem ersten Gespräch abgeschlossen haben, gehen Sie zu **Design Websites** , um die Websitearchitektur zu definieren. Um diese Option abzuschließen, fahren Sie mit Schritt 3 fort.
    
      - **Option 2: Entwerfen von Websites**     Durch Klicken auf **Design Sites** auf der Willkommensseite werden die im Abschnitt **Erste Schritte** dargestellten Interview Fragen umgangen. Die Informationen, die durch Antworten auf das Interview Fragen im Abschnitt **Erste Schritte** gesammelt worden wären, werden mit dieser Option auf Standardwerte festgelegt. Durch Klicken auf **Websites entwerfen**kann der erfahrene Designer das ursprüngliche Interview umgehen und die Standardwerte bei Bedarf auf der Startseite der **zentralen Websites** ändern. Um diese Option abzuschließen, überspringen Sie die Schritte 3-5, und beginnen Sie mit Schritt 6.
    
      - **Option 3: Anzeigen der gespeicherten Topologie**     Wenn Sie eine Topologie bereits durch vorherige Verwendung des Planungstools abgeschlossen und gespeichert haben, können Sie die meisten dieser Schritte überspringen und mit dem Öffnen und Anzeigen der Topologie beginnen. Sie können auch Änderungen und Aktualisierungen an der Topologie vornehmen, Sie erneut speichern und dann in Microsoft Excel oder Microsoft Visio exportieren. Um diese Option abzuschließen, überspringen Sie die Schritte 3-12, und beginnen Sie mit Schritt 13.

3.  Klicken Sie auf **Erste Schritte** , um mit dem Entwerfen Ihrer lync Server 2013 Topologie zu beginnen.

4.  Beantworten Sie die einzelnen Abschnitte, indem Sie die entsprechenden Kriterien für Ihren Entwurf auswählen, und klicken Sie dann auf **weiter** , um zur nächsten Assistentenseite zu gelangen. Klicken Sie auf **zurück** , um Änderungen auf vorherigen Seiten vorzunehmen.
    
    <div>
    

    > [!TIP]  
    > Jede Seite enthält eine Beschreibung der Auswahlkriterien und Empfehlungen basierend auf bevorzugten Methoden und Kapazitätsplanung. Wenn Sie weitere Informationen benötigen <STRONG>, klicken Sie auf Weitere Informationen</STRONG> , um detaillierte Informationen aus der lync Server 2013 Planungsdokumentation auf der Microsoft TechNet-Website zu lesen. Für den Zugriff auf die Microsoft TechNet-Website benötigen Sie eine Internet Verbindung.

    
    </div>

5.  Wählen Sie die entsprechenden Optionen für Ihren Entwurf aus. Nachdem die anfänglichen Kriterien definiert wurden, wird eine Seite bestätigen, dass ihre Features-Übersicht abgeschlossen ist.

6.  Klicken Sie auf **Websites entwerfen** , um Ihren zentralen Standort zu definieren.
    
    <div>
    

    > [!NOTE]  
    > Für jede lync Server 2013 Topologie ist mindestens ein zentraler Standort erforderlich. Ihr Entwurf kann einen einzelnen zentralen Standort, einen zentralen Standort mit einer Reihe von Zweigstellenstandorten, eine Reihe von zentralen Standorten oder eine Reihe von zentralen Standorten mit Zweigstellenstandorten aufweisen, die jedem zentralen Standort zugeordnet sind.

    
    </div>

7.  Geben Sie unter **Websitename**den Namen ein, mit dem dieser zentrale Standort identifiziert wird.

8.  Geben Sie unter **Standort verwaltete Benutzer**die erwartete Anzahl von lokalen gleichzeitigen Benutzern ein, die an diesem zentralen Standort verwaltet werden sollen.

9.  Geben Sie in in der Cloud vernetzte **Benutzer**die erwartete Anzahl gleichzeitiger Online Benutzer ein, die an diesem zentralen Standort verwaltet werden sollen.

10. Ändern Sie bei Bedarf die Auswahlmöglichkeiten für Online Zusammenarbeit, Benutzer, VoIP, zusätzliche Bereitstellungsoptionen oder Server Anwendungen.
    
    <div>
    

    > [!IMPORTANT]  
    > Zu diesem Zeitpunkt im Entwurf können Sie nur Optionen für Ihre Bereitstellung auswählen oder deaktivieren. Sie können jedoch in einer späteren Phase des Planungstools weitere Optionen konfigurieren. Es gibt auch Optionen, die nicht verfügbar sind und nicht gelöscht werden können. Darüber hinaus müssen Sie möglicherweise eine Option deaktivieren, um eine andere zu löschen. Wenn Sie beispielsweise die <STRONG>Enterprise-VoIP</STRONG> -Option unter VoIP deaktivieren, werden die Optionen <STRONG>Reaktionsgruppe</STRONG>, <STRONG>Ankündigung</STRONG>und <STRONG>Anruf parken</STRONG> unter Server Anwendungen (alle Features von Enterprise-VoIP) ebenfalls gelöscht.

    
    </div>

11. Nachdem Sie einen Websitenamen und die Anzahl der Benutzerdefiniert haben, klicken Sie auf **weiter**.

12. Auf den folgenden Seiten werden Informationen zu SIP-Domänen, Konferenzeinstellungen, VoIP-Einstellungen und-Infrastruktur, Exchange um, externer Benutzer Zugriff, Einstellungen für beständigen Chat, Clienteinstellungen, Zusammenstellungsoptionen und Zweigstellen Sites abgefragt. Beantworten Sie diese Fragen entsprechend.

13. In der letzten Frage werden Sie gefragt, ob Sie einen anderen zentralen Standort erstellen möchten. Wenn Sie **Ja**auswählen, kehrt das Planungs Tool zur Seite Zentrale Standorte zurück. Wenn Sie **Nein**auswählen, klicken Sie auf **weiter**, und klicken Sie dann auf **Zeichnen** , um die Ansicht globaler Topologie auf hoher Ebene anzuzeigen.

14. Klicken Sie auf **anzeigen**, um eine vorhandene Topologie anzuzeigen.

15. Klicken Sie auf die XML-Datei, die die zuvor gespeicherte Topologie darstellt, und klicken Sie dann auf **Öffnen**.

16. Das Planungs Tool zeigt die Seite globale Topologie an. Sie können jetzt mit der Bearbeitung, Aktualisierung oder Änderung der Topologie beginnen, indem Sie die Tools verwenden, die im Planungs Tool zur Verfügung stehen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bearbeiten des Entwurfs in lync Server 2013](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

