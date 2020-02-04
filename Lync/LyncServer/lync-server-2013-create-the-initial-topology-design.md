---
title: 'Lync Server 2013: Erstellen des anfänglichen Topologie-Designs'
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
ms.openlocfilehash: 7fc8d3e731c2772b275dd861c41b8c10f2127a2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a>Erstellen des anfänglichen Topologie-Designs für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Nachdem Sie die Installation von lync Server 2013, Planungstool, abgeschlossen haben, können Sie das Planungstool starten und mit dem Entwerfen der vorgeschlagenen lync Server 2013-Infrastruktur beginnen.

<div>


> [!NOTE]  
> Das Planungstool ist ein Assistenten gesteuertes Tool mit detaillierten Leitfäden, mit deren Hilfe Sie Ihre Entscheidungsfindung beim Entwerfen Ihrer Websites und Topologie unterrichten können. Dieses Thema ist nicht als umfassender Leitfaden zu verstehen, sondern dient lediglich dazu, Ihnen bei der Verwendung des Planungstools in ihren Entwurfs Sitzungen zu helfen.



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>So beginnen Sie mit der Verwendung des Planungstools und Erstellen des anfänglichen Entwurfs

1.  Starten Sie lync Server 2013, Planungstool: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **Planungstool**.

2.  Nachdem das Planungstool gestartet wurde, wird die Seite **Willkommen bei Planning Tool für Microsoft lync Server 2013** angezeigt. Wählen Sie eine der folgenden Optionen, um zu beginnen:
    
      - **Option 1: Erste Schritte**   beim Klicken auf " **Erste Schritte** " finden Sie eine bestimmte Reihe von Interview Fragen mit relevanten Auswahlmöglichkeiten, um die Kriterien zu definieren. Fahren Sie nach Beantwortung der anfänglichen Fragen in **Erste Schritte** mit dem Abschnitt **Standorte entwerfen** fort, um die Architektur Ihres Standorts zu definieren. Fahren Sie mit Schritt 3 fort, um diese Option abzuschließen.
    
      - **Option 2: Design Websites**   Wenn Sie auf der Willkommensseite auf **Design Websites** klicken, werden die im Abschnitt **Erste Schritte** vorgestellten Fragen im Interview umgangen. Die Informationen, die anhand der Fragen im Abschnitt **Erste Schritte** erfasst worden wären, werden bei Auswahl dieser Option auf Standardwerte gesetzt. Durch Klicken auf **Standorte entwerfen** können erfahrene Nutzer, die für den Entwurf verantwortlich sind, die anfänglichen Fragen umgehen und die Standardwerte nach Bedarf auf der Startseite für den Abschnitt **Zentrale Standorte** ändern. Überspringen Sie die Schritte 3–5, und beginnen Sie mit Schritt 6, um diese Option abzuschließen.
    
      - **Option 3: Anzeigen der gespeicherten Topologie**   Wenn Sie bereits eine Topologie durch vorherige Verwendung des Planungstools abgeschlossen und gespeichert haben, können Sie die meisten dieser Schritte überspringen und zunächst die Topologie öffnen und anzeigen. Sie können die Topologie ändern, aktualisieren, erneut speichern und anschließend nach Microsoft Excel oder Microsoft Visio exportieren. Überspringen Sie die Schritte 3–12 und beginnen Sie mit Schritt 13, um diese Option abzuschließen.

3.  Klicken Sie auf **Erste Schritte** , um mit dem Entwerfen Ihrer lync Server 2013-Topologie zu beginnen.

4.  Beantworten Sie die Fragen in jedem Abschnitt, indem Sie die geeigneten Kriterien für Ihren Entwurf auswählen, und klicken Sie anschließend auf **Weiter**, um mit der nächsten Seite des Assistenten fortzufahren. Klicken Sie auf **Zurück**, um Änderungen auf vorherigen Seiten vorzunehmen.
    
    <div>
    

    > [!TIP]  
    > Jede Seite bietet eine Beschreibung der Auswahlkriterien sowie Empfehlungen basierend auf bevorzugten Vorgehensweisen und der Kapazitätsplanung. Wenn Sie weitere Informationen benötigen <STRONG>, klicken Sie auf Weitere Informationen</STRONG> , um detaillierte Informationen aus der lync Server 2013-Planungsdokumentation auf der Microsoft TechNet-Website zu lesen. Für den Zugriff auf die Microsoft TechNet-Website ist eine Internetverbindung erforderlich.

    
    </div>

5.  Wählen Sie die geeigneten Optionen für Ihren Entwurf. Nach der Definition der anfänglichen Kriterien werden Sie darüber informiert, dass die Funktionsübersicht vollständig ist.

6.  Klicken Sie auf **Websites entwerfen** , um Ihre zentrale Website zu definieren.
    
    <div>
    

    > [!NOTE]  
    > Jede lync Server 2013-Topologie verfügt über mindestens einen zentralen Standort. Ihr Entwurf kann eine einzige zentrale Website, einen zentralen Standort mit einer Reihe von Zweigstellen, eine Reihe von zentralen Standorten oder eine Reihe zentraler Standorte mit Verzweigungs Websites aufweisen, die jedem zentralen Standort zugeordnet sind.

    
    </div>

7.  Geben Sie unter **Websitename**den Namen ein, der diese zentrale Website kennzeichnet.

8.  Geben Sie in "Website-vernetzte **Benutzer**" die erwartete Anzahl von lokalen gleichzeitigen Benutzern ein, die an diesem zentralen Standort verwaltet werden sollen.

9.  Geben Sie in Cloud-vernetzten **Benutzern**die erwartete Anzahl von gleichzeitigen Online Benutzern ein, die in diesem zentralen Standort verwaltet werden sollen.

10. Ändern Sie nach Bedarf die Auswahl für Onlinezusammenarbeit, Benutzer, VoIP, zusätzliche Bereitstellungsoptionen oder Serveranwendungen.
    
    <div>
    

    > [!IMPORTANT]  
    > Zu diesem Entwurfszeitpunkt können Sie Optionen für Ihre Bereitstellung nur auswählen oder deaktivieren. Sie können jedoch in einer späteren Phase des Planungstools weitere Optionen konfigurieren. Einige Optionen sind nicht verfügbar und können nicht deaktiviert werden. Darüber hinaus müssen Sie möglicherweise eine Option deaktivieren, um eine andere deaktivieren zu können. Wenn Sie zum Beispiel unter „VoIP“ die Option <STRONG>Enterprise-VoIP</STRONG> deaktivieren, sind unter „Serveranwendungen“ die Optionen <STRONG>Reaktionsgruppe</STRONG>, <STRONG>Ankündigung</STRONG> und <STRONG>Anruf parken</STRONG> deaktiviert.

    
    </div>

11. Klicken Sie nach dem Definieren von Standortname und Nutzeranzahl auf **Weiter**.

12. Auf den folgenden Seiten werden Informationen zu SIP-Domänen, Konferenzeinstellungen, Spracheinstellungen und-Infrastruktur, Exchange um-, externer Benutzer Zugriff, Einstellungen für beständigen Chat, Clienteinstellungen, Zusammenstellungsoptionen und Verzweigungs Websites verlangt. Geben Sie die entsprechenden Informationen an.

13. In der letzten Frage wird gefragt, ob Sie eine weitere zentrale Website erstellen möchten. Wenn Sie **Ja**auswählen, kehrt das Planungs Tool zur Seite "zentrale Websites" zurück. Wenn Sie **Nein** auswählen, klicken Sie auf **Weiter** und anschließend auf **Zeichnen**, um die allgemeine Übersicht über die globale Technologie anzuzeigen.

14. Klicken Sie zum Anzeigen einer vorhandenen Topologie auf **Anzeigen**.

15. Klicken Sie auf die XML-Datei, welche die zuvor gespeicherte Topologie enthält, und klicken Sie auf **Öffnen**.

16. Das Planungs Tool zeigt die Seite globale Topologie an. Mit den im Planungs Tool verfügbaren Tools können Sie nun mit dem Bearbeiten, aktualisieren oder Ändern der Topologie beginnen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bearbeiten des Entwurfs in Lync Server 2013](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

