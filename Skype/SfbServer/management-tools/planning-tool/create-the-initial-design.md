---
title: Erstellen des anfänglichen Topologieentwurfs für Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: Nachdem Sie die Installation des Skype for Business Server-Planungstools abgeschlossen haben, können Sie mit dem Planungstool beginnen und mit dem Entwerfen der vorgeschlagenen Skype for Business Server 2015-Infrastruktur beginnen.
ms.openlocfilehash: b5590e3bfdf97a6816421a2164712b069884793958be1dbf38eba1d50ef95592
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347940"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>Erstellen des anfänglichen Topologieentwurfs für Skype for Business Server 2015

Nachdem Sie die Installation des Skype for Business Server-Planungstools abgeschlossen haben, können Sie mit dem Planungstool beginnen und mit dem Entwerfen der vorgeschlagenen Skype for Business Server 2015-Infrastruktur beginnen.

> [!NOTE]
>  Das Planungstool ist ein assistentengesteuertes Tool mit detaillierten Anleitungen, die Sie bei der Entscheidungsfindung beim Entwerfen Ihrer Standorte und Topologie informieren. Dieses Thema ist nicht als vollständige Anleitung gedacht, sondern soll Ihnen einfach helfen, das Planungstool in Ihren Entwurfssitzungen zu verwenden.

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Erste Schritte mit dem Planungstool und Erstellen des anfänglichen Designs

1. Starten Sie das Skype for Business Server 2015-Planungstool: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business Server 2015"** und dann auf **"Planungstool".**

2. Nachdem das Planungstool gestartet wurde, wird die Seite **"Willkommen beim Planungstool für Skype for Business Server 2015"** angezeigt. Wählen Sie eine der folgenden Optionen aus, um mit dem Entwurf zu beginnen:

   - **Option 1: Erste Schritte** Durch Klicken auf **Erste Schritte** erhalten Sie eine bestimmte Reihe von Fragen mit relevanten Auswahlen, um die Kriterien zu definieren. Nachdem Sie die anfängliche **Erste Schritte** Interviewabschnitt abgeschlossen haben, fahren Sie mit dem **Abschnitt "Websites entwerfen"** fort, um Ihre Websitearchitektur zu definieren. Fahren Sie mit Schritt 3 fort, um diese Option abzuschließen.

   - **Option 2: Entwerfen von Websites** Wenn Sie auf der Willkommensseite auf **"Websites entwerfen"** klicken, werden die Fragen im **Erste Schritte** umgangen. Die Informationen, die durch Antworten auf die Fragen im **Erste Schritte** Abschnitt gesammelt worden wären, werden mit dieser Option auf Standardwerte festgelegt. Durch Klicken auf **"Websites entwerfen"** kann der erfahrene Designer das anfängliche Interview umgehen und die Standardwerte nach Bedarf auf der Startseite **"Zentrale Websites"** ändern. Um diese Option abzuschließen, überspringen Sie die Schritte 3 bis 5, und beginnen Sie mit Schritt 6.

   - **Option 3: Anzeigen der gespeicherten Topologie** Wenn Sie eine Topologie bereits durch vorherige Verwendung des Planungstools abgeschlossen und gespeichert haben, können Sie die meisten dieser Schritte überspringen und zunächst die Topologie öffnen und anzeigen. Sie können auch Änderungen und Aktualisierungen an der Topologie vornehmen, sie erneut speichern und dann in Microsoft Excel oder Microsoft Visio exportieren. Um diese Option abzuschließen, überspringen Sie die Schritte 3 bis 12, und beginnen Sie mit Schritt 13.

3. Klicken Sie auf **Erste Schritte,** um mit dem Entwerfen Ihrer Skype for Business Server 2015-Topologie zu beginnen.

4. Beantworten Sie jeden Abschnitt, indem Sie die entsprechenden Kriterien für Ihren Entwurf auswählen, und klicken Sie dann auf **"Weiter",** um mit der nächsten Assistentenseite fortzufahren. Klicken Sie auf **"Zurück",** um Änderungen auf vorherigen Seiten vorzunehmen.

    > [!TIP]
    > Jede Seite enthält eine Beschreibung der Auswahlkriterien und Empfehlungen basierend auf den bevorzugten Methoden und der Kapazitätsplanung. Wenn Sie weitere Details benötigen, klicken Sie auf **"Weitere Informationen",** um detaillierte Informationen aus der Skype for Business Server 2015-Planungsdokumentation auf der Microsoft-Website zu lesen. Sie benötigen eine Internetverbindung, um auf die Microsoft-Website zugreifen zu können.

5. Wählen Sie die geeigneten Optionen für Ihr Design aus. Nachdem die anfänglichen Kriterien definiert wurden, wird auf einer Seite bestätigt, dass ihre Features-Übersicht abgeschlossen ist.

6. Klicken Sie auf **"Websites entwerfen",** um Ihren zentralen Standort zu definieren.

    > [!NOTE]
    > Jede Skype for Business Server 2015-Topologie hat mindestens einen zentralen Standort. Ihr Entwurf kann einen zentralen Standort, einen zentralen Standort mit einer Reihe von Zweigstellen, eine Reihe von zentralen Standorten oder eine Reihe von zentralen Standorten mit Zweigstellen haben, die jedem zentralen Standort zugeordnet sind.

7. Geben Sie unter **"Standortname"** den Namen ein, der diesen zentralen Standort identifiziert.

8. Geben Sie unter **"Verwaltete Benutzer"** die erwartete Anzahl von lokalen gleichzeitigen Benutzern ein, die an diesem zentralen Standort verwaltet werden.

9. Geben Sie in **"Cloud-verwaltete Benutzer"** die erwartete Anzahl gleichzeitiger Onlinebenutzer ein, die an diesem zentralen Standort verwaltet werden.

10. Ändern Sie bei Bedarf die Auswahl für Onlinezusammenarbeit, Benutzer, VoIP, zusätzliche Bereitstellungsoptionen oder Serveranwendungen.

    > [!IMPORTANT]
    > An diesem Punkt im Entwurf können Sie nur Optionen für Ihre Bereitstellung auswählen oder deaktivieren. Sie können jedoch in einer späteren Phase des Planungstool weitere Optionen konfigurieren. Es gibt auch Optionen, die nicht verfügbar sind und nicht gelöscht werden können. Darüber hinaus müssen Sie möglicherweise eine Option deaktivieren, um eine andere zu löschen. Wenn Sie z. B. die **Option Enterprise-VoIP** unter "VoIP" deaktivieren, werden auch die Optionen **"Reaktionsgruppe",** **"Ansage"** und **"Anruf parken"** unter "Serveranwendungen" (die alle Features von Enterprise-VoIP sind) deaktiviert.

11. Klicken Sie nach dem Definieren eines Websitenamens und der Anzahl der Benutzer auf **"Weiter".**

12. Auf den folgenden Seiten werden Informationen zu SIP-Domänen, Konferenzeinstellungen, VoIP-Einstellungen und Infrastruktur, Exchange UM, Zugriff externer Benutzer, Einstellungen für beständigen Chat, Clienteinstellungen, Kollokationsoptionen und Zweigstellen angefordert. Beantworten Sie diese Fragen nach Bedarf.

13. Die letzte Frage stellt sich, ob Sie einen anderen zentralen Standort erstellen möchten. Wenn Sie **"Ja"** auswählen, kehrt das Planungstool zur Seite "Zentrale Standorte" zurück. Wenn Sie **"Nein"** auswählen, klicken Sie auf **"Weiter"** und dann auf **"Zeichnen",** um die allgemeine Ansicht "Globale Topologie" anzuzeigen.

14. Klicken Sie zum Anzeigen einer vorhandenen Topologie auf **"Anzeigen".**

15. Klicken Sie auf die .xml Datei, die die zuvor gespeicherte Topologie darstellt, und klicken Sie dann auf **"Öffnen".**

16. Das Planungstool zeigt die Seite "Globale Topologie" an. Sie können nun mit dem Bearbeiten, Aktualisieren oder Ändern der Topologie beginnen, indem Sie die im Planungstool verfügbaren Tools verwenden.

## <a name="see-also"></a>Siehe auch

[Bearbeiten des Entwurfs](/previous-versions/office/lync-server-2013/lync-server-2013-editing-the-design)