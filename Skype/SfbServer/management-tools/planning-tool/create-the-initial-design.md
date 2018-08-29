---
title: Erstellen des anfänglichen Topologieentwurfs für Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: Nach dem Installieren der Skype für Business Server-Planungstool können Sie zum Starten des Planungstools und mit dem Entwerfen der vorgeschlagenen Skype für Business Server 2015-Infrastruktur beginnen.
ms.openlocfilehash: 73fd6f4a83ec5aec6808124728c1c73419bcdd28
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23246666"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>Erstellen des anfänglichen Topologieentwurfs für Skype for Business Server 2015

Nach dem Installieren der Skype für Business Server-Planungstool können Sie zum Starten des Planungstools und mit dem Entwerfen der vorgeschlagenen Skype für Business Server 2015-Infrastruktur beginnen.

> [!NOTE]
>  Das Planungstool ist ein Assistent-gesteuerte Tool mit ausführliche Anleitungen zur Ihren Entscheidungsprozess beim Entwerfen Ihrer Websites und die Topologie zu informieren. In diesem Thema wird nicht als eine vollständige Anleitung, sondern einfach zu helfen Ihnen den Einstieg Verwenden des Planungstools in Ihrer entwurfssitzung vorgesehen.

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Erste Schritte mit dem Planungstool und Erstellen des anfänglichen Entwurfs

1. Starten Sie die Skype für Business Server 2015-Planungstool: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server 2015**, und klicken Sie dann auf **Planungstool**.

2. Nachdem das Planungstool gestartet wurde, wird die Seite **Willkommen zum Planungstool für Skype für Business Server 2015** angezeigt. Wählen Sie eine der folgenden Optionen, um zu beginnen:

   - **Option 1: Erste Schritte** Klicken Sie auf **Erste Schritte** bietet eine bestimmte Reihe von Fragen relevanten Auswahlen die Kriterien definieren. Fahren Sie nach Beantwortung der anfänglichen Fragen in **Erste Schritte** mit dem Abschnitt **Standorte entwerfen** fort, um die Architektur Ihres Standorts zu definieren. Fahren Sie mit Schritt 3 fort, um diese Option abzuschließen.

   - **Option 2: Entwerfen von Websites** **Design Sites** auf der Seite Willkommen auf umgeht die Gespräch Fragen im Abschnitt **Erste Schritte** . Die Informationen, die anhand der Fragen im Abschnitt **Erste Schritte** erfasst worden wären, werden bei Auswahl dieser Option auf Standardwerte gesetzt. Durch Klicken auf **Standorte entwerfen** können erfahrene Nutzer, die für den Entwurf verantwortlich sind, die anfänglichen Fragen umgehen und die Standardwerte nach Bedarf auf der Startseite für den Abschnitt **Zentrale Standorte** ändern. Überspringen Sie die Schritte 3–5, und beginnen Sie mit Schritt 6, um diese Option abzuschließen.

   - **Option 3: Ihre gespeicherte Topologie anzeigen** Wenn Sie bereits abgeschlossen und eine Topologie über vorherige Verwendung des Planungstools gespeichert haben, können Sie die meisten Schritte überspringen und starten, indem Sie öffnen und Anzeigen der Topologie. Sie können die Topologie ändern, aktualisieren, erneut speichern und anschließend nach Microsoft Excel oder Microsoft Visio exportieren. Überspringen Sie die Schritte 3–12 und beginnen Sie mit Schritt 13, um diese Option abzuschließen.

3. Klicken Sie auf **Erste Schritte** , um mit dem Entwerfen Ihrer Skype für Business Server 2015 Topologie beginnen.

4. Beantworten Sie die Fragen in jedem Abschnitt, indem Sie die geeigneten Kriterien für Ihren Entwurf auswählen, und klicken Sie anschließend auf **Weiter**, um mit der nächsten Seite des Assistenten fortzufahren. Klicken Sie auf **Zurück**, um Änderungen auf vorherigen Seiten vorzunehmen.

    > [!TIP]
    > Jede Seite bietet eine Beschreibung der Auswahlkriterien sowie Empfehlungen basierend auf bevorzugten Vorgehensweisen und der Kapazitätsplanung. Wenn Sie weitere Informationen benötigen, klicken Sie auf **Weitere** , um detaillierte Informationen aus der Skype für Business Server 2015 in der Planungsdokumentation auf der Microsoft-Website zu lesen. Sie müssen Internet Connectivity greifen Sie auf der Microsoft-Website verfügen.

5. Wählen Sie die geeigneten Optionen für Ihren Entwurf. Nach der Definition der anfänglichen Kriterien werden Sie darüber informiert, dass die Funktionsübersicht vollständig ist.

6. Klicken Sie auf **Design Sites** , um Ihre zentralen Standort zu definieren.

    > [!NOTE]
    > Jede Skype für Business Server 2015 Topologie müssen mindestens einen zentralen Standort. Ihres Entwurfs möglicherweise eine einzelne zentralen Standort, einer zentralen Website mit einer Anzahl von Zweigniederlassungen, eine Anzahl von zentralen Standorten oder eine Anzahl von zentralen Standorten mit Zweigniederlassungen jeder zentrale Standort zugeordnet.

7. Geben Sie in das Feld **Websitename**den Namen, der diese zentralen Standort identifiziert werden können.

8. Geben Sie im **Websitebenutzer verwaltet**die erwartete Anzahl von lokalen gleichzeitige Benutzer, die in dieser zentralen Standort verwaltet wird.

9. Geben Sie in der **Cloud verwaltet Benutzer**die erwartete Anzahl der online gleichzeitige Benutzer, die in dieser zentralen Standort verwaltet wird.

10. Ändern Sie nach Bedarf die Auswahl für Onlinezusammenarbeit, Benutzer, VoIP, zusätzliche Bereitstellungsoptionen oder Serveranwendungen.

    > [!IMPORTANT]
    > Zu diesem Entwurfszeitpunkt können Sie Optionen für Ihre Bereitstellung nur auswählen oder deaktivieren. Sie können jedoch weitere Optionen in einer späteren Phase des Planungstool konfigurieren. Einige Optionen sind nicht verfügbar und können nicht deaktiviert werden. Darüber hinaus müssen Sie möglicherweise eine Option deaktivieren, um eine andere deaktivieren zu können. Wenn Sie zum Beispiel unter „VoIP“ die Option **Enterprise-VoIP** deaktivieren, sind unter „Serveranwendungen“ die Optionen **Reaktionsgruppe**, **Ankündigung** und **Anruf parken** deaktiviert.

11. Klicken Sie nach dem Definieren von Standortname und Nutzeranzahl auf **Weiter**.

12. Bitten Sie die folgenden Seiten Informationen zu SIP-Domänen, konferenzeinstellungen, VoIP-Einstellungen und Infrastruktur, Exchange UM, Zugriff durch externe Benutzer, beständigen Chat Einstellungen, Clienteinstellungen, Kollokation Optionen und Zweigniederlassungen. Geben Sie die entsprechenden Informationen an.

13. Die letzte Frage gefragt werden, wenn Sie einen anderen zentralen Standort erstellen möchten. Wenn Sie **Ja**auswählen, gibt das Planungstool zur zentralen Standorten Seite zurück. Wenn Sie **Nein** auswählen, klicken Sie auf **Weiter** und anschließend auf **Zeichnen**, um die allgemeine Übersicht über die globale Technologie anzuzeigen.

14. Klicken Sie zum Anzeigen einer vorhandenen Topologie auf **Anzeigen**.

15. Klicken Sie auf die XML-Datei, welche die zuvor gespeicherte Topologie enthält, und klicken Sie auf **Öffnen**.

16. Das Planungstool zeigt die Seite globale Topologie. Jetzt können Sie bearbeiten, aktualisieren oder Ändern der Topologie mithilfe der Tools in das Planungstool beginnen.

## <a name="see-also"></a>Siehe auch

[Bearbeiten des Entwurfs](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)