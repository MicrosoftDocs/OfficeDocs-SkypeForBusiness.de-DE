---
title: Erstellen des anfänglichen Topologieentwurfs für Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: Nachdem Sie die Installation des Skype for Business Server-Planungstools abgeschlossen haben, sind Sie bereit, das Planungstool zu starten und mit dem Entwerfen der vorgeschlagenen Skype for Business Server 2015-Infrastruktur zu beginnen.
ms.openlocfilehash: 47a3725c1307bd6efe57fa07a955004bd6e5ff29
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274270"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>Erstellen des anfänglichen Topologieentwurfs für Skype for Business Server 2015

Nachdem Sie die Installation des Skype for Business Server-Planungstools abgeschlossen haben, sind Sie bereit, das Planungstool zu starten und mit dem Entwerfen der vorgeschlagenen Skype for Business Server 2015-Infrastruktur zu beginnen.

> [!NOTE]
>  Das Planungstool ist ein Assistenten gesteuertes Tool mit detaillierten Leitfäden, mit deren Hilfe Sie Ihre Entscheidungsfindung beim Entwerfen Ihrer Websites und Topologie unterrichten können. Dieses Thema ist nicht als umfassender Leitfaden zu verstehen, sondern dient lediglich dazu, Ihnen bei der Verwendung des Planungstools in ihren Entwurfs Sitzungen zu helfen.

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>So beginnen Sie mit der Verwendung des Planungstools und Erstellen des anfänglichen Entwurfs

1. Starten Sie das Planungstool für Skype for Business Server 2015: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server 2015**, und klicken Sie dann auf **Planungstool**.

2. Nach dem Start des Planungstools wird die Seite **Willkommen beim Planning Tool für Skype for Business Server 2015** angezeigt. Wählen Sie eine der folgenden Optionen, um zu beginnen:

   - **Option 1: Erste Schritte** Durch Klicken auf " **Erste Schritte" erhalten Sie** eine bestimmte Reihe von Interview Fragen mit relevanten Auswahlmöglichkeiten, um die Kriterien zu definieren. Fahren Sie nach Beantwortung der anfänglichen Fragen in **Erste Schritte** mit dem Abschnitt **Standorte entwerfen** fort, um die Architektur Ihres Standorts zu definieren. Fahren Sie mit Schritt 3 fort, um diese Option abzuschließen.

   - **Option 2: Entwerfen von Websites** Wenn Sie auf der Willkommensseite auf " **Websites entwerfen** " klicken, werden die im Abschnitt " **Erste Schritte** " vorgestellten Fragen im Interview umgangen. Die Informationen, die anhand der Fragen im Abschnitt **Erste Schritte** erfasst worden wären, werden bei Auswahl dieser Option auf Standardwerte gesetzt. Durch Klicken auf **Standorte entwerfen** können erfahrene Nutzer, die für den Entwurf verantwortlich sind, die anfänglichen Fragen umgehen und die Standardwerte nach Bedarf auf der Startseite für den Abschnitt **Zentrale Standorte** ändern. Überspringen Sie die Schritte 3–5, und beginnen Sie mit Schritt 6, um diese Option abzuschließen.

   - **Option 3: Anzeigen der gespeicherten Topologie** Wenn Sie bereits eine Topologie durch die vorherige Verwendung des Planungstools abgeschlossen und gespeichert haben, können Sie die meisten dieser Schritte überspringen und beginnen, indem Sie die Topologie öffnen und anzeigen. Sie können die Topologie ändern, aktualisieren, erneut speichern und anschließend nach Microsoft Excel oder Microsoft Visio exportieren. Überspringen Sie die Schritte 3–12 und beginnen Sie mit Schritt 13, um diese Option abzuschließen.

3. Klicken Sie auf **Erste Schritte** , um mit dem Entwerfen Ihrer Skype for Business Server 2015-Topologie zu beginnen.

4. Beantworten Sie die Fragen in jedem Abschnitt, indem Sie die geeigneten Kriterien für Ihren Entwurf auswählen, und klicken Sie anschließend auf **Weiter**, um mit der nächsten Seite des Assistenten fortzufahren. Klicken Sie auf **Zurück**, um Änderungen auf vorherigen Seiten vorzunehmen.

    > [!TIP]
    > Jede Seite bietet eine Beschreibung der Auswahlkriterien sowie Empfehlungen basierend auf bevorzugten Vorgehensweisen und der Kapazitätsplanung. Wenn Sie weitere Informationen benötigen, klicken **** Sie auf Weitere Informationen, um detaillierte Informationen aus der Skype for Business Server 2015-Planungsdokumentation auf der Microsoft-Website zu lesen. Sie müssen über eine Internet Verbindung verfügen, um auf die Microsoft-Website zugreifen zu können.

5. Wählen Sie die geeigneten Optionen für Ihren Entwurf. Nach der Definition der anfänglichen Kriterien werden Sie darüber informiert, dass die Funktionsübersicht vollständig ist.

6. Klicken Sie auf **Websites entwerfen** , um Ihre zentrale Website zu definieren.

    > [!NOTE]
    > Jede Skype for Business Server 2015-Topologie verfügt über mindestens einen zentralen Standort. Ihr Entwurf kann eine einzige zentrale Website, einen zentralen Standort mit einer Reihe von Zweigstellen, eine Reihe von zentralen Standorten oder eine Reihe zentraler Standorte mit Verzweigungs Websites aufweisen, die jedem zentralen Standort zugeordnet sind.

7. Geben Sie unter **Websitename**den Namen ein, der diese zentrale Website kennzeichnet.

8. Geben Sie in "Website-vernetzte **Benutzer**" die erwartete Anzahl von lokalen gleichzeitigen Benutzern ein, die an diesem zentralen Standort verwaltet werden sollen.

9. Geben Sie in Cloud-vernetzten **Benutzern**die erwartete Anzahl von gleichzeitigen Online Benutzern ein, die in diesem zentralen Standort verwaltet werden sollen.

10. Ändern Sie nach Bedarf die Auswahl für Onlinezusammenarbeit, Benutzer, VoIP, zusätzliche Bereitstellungsoptionen oder Serveranwendungen.

    > [!IMPORTANT]
    > Zu diesem Entwurfszeitpunkt können Sie Optionen für Ihre Bereitstellung nur auswählen oder deaktivieren. Sie können jedoch in einer späteren Phase des Planungstools weitere Optionen konfigurieren. Einige Optionen sind nicht verfügbar und können nicht deaktiviert werden. Darüber hinaus müssen Sie möglicherweise eine Option deaktivieren, um eine andere deaktivieren zu können. Wenn Sie zum Beispiel unter „VoIP“ die Option **Enterprise-VoIP** deaktivieren, sind unter „Serveranwendungen“ die Optionen **Reaktionsgruppe**, **Ankündigung** und **Anruf parken** deaktiviert.

11. Klicken Sie nach dem Definieren von Standortname und Nutzeranzahl auf **Weiter**.

12. Auf den folgenden Seiten werden Informationen zu SIP-Domänen, Konferenzeinstellungen, Spracheinstellungen und-Infrastruktur, Exchange um-, externer Benutzer Zugriff, Einstellungen für beständigen Chat, Clienteinstellungen, Zusammenstellungsoptionen und Verzweigungs Websites verlangt. Geben Sie die entsprechenden Informationen an.

13. In der letzten Frage wird gefragt, ob Sie eine weitere zentrale Website erstellen möchten. Wenn Sie **Ja**auswählen, kehrt das Planungs Tool zur Seite "zentrale Websites" zurück. Wenn Sie **Nein** auswählen, klicken Sie auf **Weiter** und anschließend auf **Zeichnen**, um die allgemeine Übersicht über die globale Technologie anzuzeigen.

14. Klicken Sie zum Anzeigen einer vorhandenen Topologie auf **Anzeigen**.

15. Klicken Sie auf die XML-Datei, welche die zuvor gespeicherte Topologie enthält, und klicken Sie auf **Öffnen**.

16. Das Planungs Tool zeigt die Seite globale Topologie an. Mit den im Planungs Tool verfügbaren Tools können Sie nun mit dem Bearbeiten, aktualisieren oder Ändern der Topologie beginnen.

## <a name="see-also"></a>Siehe auch

[Editing the Design](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
