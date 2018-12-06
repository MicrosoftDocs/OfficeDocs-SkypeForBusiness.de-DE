---
title: 'Lync Server 2013: Erstellen des anfänglichen Entwurfs'
TOCTitle: Erstellen des anfänglichen Entwurfs
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615047(v=OCS.15)
ms:contentKeyID: 52056492
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen des anfänglichen Entwurfs für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Nachdem Sie die Installation des Lync Server 2013, Planungstools abgeschlossen haben, können Sie das Planungstool starten und mit dem Entwerfen der vorgeschlagenen Lync Server 2013-Infrastruktur beginnen.


> [!NOTE]
> Das Planungstool ist ein assistentengestütztes Tool mit ausführlichen Handbüchern, um Sie beim Entscheidungsprozess beim Entwerfen Ihrer Websites und Topologie zu unterstützen. Dieses Thema ist nicht als vollständige Anleitung gedacht, sondern soll Sie lediglich bei den ersten Schritten bei der Verwendung des Planungstool bei Ihren Entwurfssitzungen unterstützen.



## So verwenden Sie das Planungstool und erstellen den anfänglichen Entwurf

1.  Starten des Planungstools von Lync Server 2013: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Planungstool**.

2.  Nachdem das Planungstool gestartet wurde, wird die Seite **Willkommen zum Planungstool für Microsoft Lync Server 2013** angezeigt. Wählen Sie eine der folgenden Optionen, um zu beginnen:
    
      - **Option 1: Erste Schritte**   Wenn Sie auf **Erste Schritte** klicken, werden Ihnen verschiedene Fragen mit relevanten Auswahlmöglichkeiten gestellt, um die Kriterien zu definieren. Fahren Sie nach Beantwortung der anfänglichen Fragen in **Erste Schritte** mit dem Abschnitt **Standorte entwerfen** fort, um die Architektur Ihres Standorts zu definieren. Fahren Sie mit Schritt 3 fort, um diese Option abzuschließen.
    
      - **Option 2: Standorte entwerfen**   Wenn Sie auf der Willkommensseite auf **Standorte entwerfen** klicken, werden die Fragen aus dem Abschnitt **Erste Schritte** nicht angezeigt. Die Informationen, die anhand der Fragen im Abschnitt **Erste Schritte** erfasst worden wären, werden bei Auswahl dieser Option auf Standardwerte gesetzt. Durch Klicken auf **Standorte entwerfen** können erfahrene Benutzer, die für den Entwurf verantwortlich sind, die anfänglichen Fragen umgehen und die Standardwerte nach Bedarf auf der Startseite für den Abschnitt **Zentrale Standorte** ändern. Überspringen Sie die Schritte 3-5, und beginnen Sie mit Schritt 6, um diese Option abzuschließen.
    
      - **Option 3: Gespeicherte Topologie anzeigen**   Wenn Sie bereits zu einem früheren Zeitpunkt mithilfe des Planungstools eine Topologie erstellt und gespeichert haben, können Sie die meisten dieser Schritte überspringen und diese Topologie direkt öffnen. Sie können die Topologie ändern, aktualisieren, erneut speichern und anschließend nach Microsoft Excel oder Microsoft Visio exportieren. Überspringen Sie die Schritte 3-12, und beginnen Sie mit Schritt 13, um diese Option abzuschließen.

3.  Klicken Sie auf **Erste Schritte** , um mit dem Entwerfen Ihrer Lync Server 2013-Topologie zu beginnen.

4.  Beantworten Sie die Fragen in jedem Abschnitt, indem Sie die geeigneten Kriterien für Ihren Entwurf auswählen, und klicken Sie anschließend auf **Weiter** , um mit der nächsten Seite des Assistenten fortzufahren. Klicken Sie auf **Zurück** , um Änderungen auf vorhergehenden Seiten vorzunehmen.
    

    > [!TIP]
    > Jede Seite bietet eine Beschreibung der Auswahlkriterien sowie Empfehlungen basierend auf bevorzugten Vorgehensweisen und der Kapazitätsplanung. Wenn Sie weitere Informationen benötigen, klicken Sie auf <STRONG>Weitere Informationen</STRONG> , um die Lync Server 2013-Planungsdokumentation auf der Microsoft TechNet-Website aufzurufen. Für den Zugriff auf die Microsoft TechNet-Website ist eine Internetverbindung erforderlich.



5.  Wählen Sie die geeigneten Optionen für Ihren Entwurf. Nach der Definition der anfänglichen Kriterien werden Sie darüber informiert, dass die Funktionsübersicht vollständig ist.

6.  Klicken Sie auf **Standorte entwerfen** , um Ihren zentraler Standort zu definieren.
    

    > [!NOTE]
    > Jede Lync Server 2013-Topologie verfügt über mindestens einen zentraler Standort. Ihr Entwurf kann einen einzelnen zentraler Standort, einen zentraler Standort mit mehreren Zweigstellenstandorten, mehrere zentrale Standorte oder mehrere zentrale Standorte mit Zweigstellenstandorten aufweisen, die dem jeweiligen zentraler Standort zugeordnet sind.



7.  Geben Sie unter **Standortname** den Namen ein, der diesen zentraler Standort identifiziert.

8.  Geben Sie unter **Standortbenutzer** die erwartete Anzahl von gleichzeitigen lokalen Benutzern ein, die sich in diesem zentraler Standort befinden werden.

9.  Geben Sie unter **Cloudbenutzer** die erwartete Anzahl von gleichzeitigen Onlinebenutzern ein, die sich in diesem zentraler Standort befinden werden.

10. Ändern Sie nach Bedarf die Auswahl für Onlinezusammenarbeit, Benutzer, VoIP, zusätzliche Bereitstellungsoptionen oder Serveranwendungen.
    

    > [!IMPORTANT]
    > Zu diesem Entwurfszeitpunkt können Sie Optionen für Ihre Bereitstellung nur auswählen oder deaktivieren. In einer späteren Phase des Planungstools können Sie jedoch weitere Optionen konfigurieren. Einige Optionen sind nicht verfügbar und können nicht deaktiviert werden. Darüber hinaus müssen Sie möglicherweise eine Option deaktivieren, um eine andere deaktivieren zu können. Wenn Sie zum Beispiel unter "VoIP" die Option <STRONG>Enterprise-VoIP</STRONG> deaktivieren, sind unter "Serveranwendungen" die Optionen <STRONG>Reaktionsgruppe</STRONG> , <STRONG>Ankündigung</STRONG> und <STRONG>Anruf parken</STRONG> deaktiviert.



11. Klicken Sie nach dem Definieren von Standortname und Benutzeranzahl auf **Weiter** .

12. Auf den folgenden Seiten werden Informationen zu SIP-Domänen, Konferenzeinstellungen, VoIP-Einstellungen und -Infrastruktur, Exchange UM, externem Benutzerzugriff, Beständiger Chat-Einstellungen, Clienteinstellungen, Kollokationsoptionen sowie Zweigstellenniederlassungen benötigt. Stellen Sie geeignete Informationen bereit.

13. Abschließend werden Sie gefragt, ob Sie einen weiteren zentraler Standort erstellen möchten. Wenn Sie **Ja** auswählen, zeigt das Planungstool erneut die Seite mit den zentralen Standorten an. Wenn Sie **Nein** auswählen, klicken Sie auf **Weiter** und dann auf **Zeichnen** , um die allgemeine Übersicht über die globale Technologie anzuzeigen.

14. Klicken Sie zum Anzeigen einer vorhandenen Topologie auf **Anzeigen** .

15. Klicken Sie auf die XML-Datei, welche die zuvor gespeicherte Topologie enthält, und klicken Sie auf **Öffnen** .

16. Das Planungstool zeigt die Seite mit der globalen Topologie an. Sie können die Topologie jetzt mithilfe der Optionen im Planungstool bearbeiten, aktualisieren oder ändern.

## Siehe auch

#### Konzepte

[Bearbeiten des Entwurfs in Lync Server 2013](lync-server-2013-editing-the-design.md)

