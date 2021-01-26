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
description: Nachdem Sie das Skype for Business Server Planning Tool installiert haben, können Sie das Planungstool starten und mit dem Entwerfen der vorgeschlagenen Skype for Business Server 2015-Infrastruktur beginnen.
ms.openlocfilehash: 7de930de8d7e194f14145c1a976fbe6b96cf234a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834965"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>Erstellen des anfänglichen Topologieentwurfs für Skype for Business Server 2015

Nachdem Sie das Skype for Business Server Planning Tool installiert haben, können Sie mit dem Planungstool beginnen und mit dem Entwerfen der vorgeschlagenen Skype for Business Server 2015-Infrastruktur beginnen.

> [!NOTE]
>  Das Planungstool ist ein assistentengesteuertes Tool mit detaillierten Anleitungen, mit dem Sie Ihre Entscheidungsfindung beim Entwerfen Ihrer Websites und Topologien unterstützen können. Dieses Thema ist nicht als vollständige Anleitung gedacht, sondern soll Ihnen lediglich dabei helfen, das Planungstool in Ihren Entwurfssitzungen zu verwenden.

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Erste Schritte mit dem Planungstool und Erstellen des anfänglichen Entwurfs

1. Starten Sie das Skype for Business Server 2015-Planungstool: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business Server 2015"** und dann auf **"Planungstool".**

2. Nachdem das Planungstool gestartet wurde, wird die Seite "Willkommen beim **Planungstool für Skype for Business Server 2015"** angezeigt. Wählen Sie eine der folgenden Optionen aus, um mit dem Entwurf zu beginnen:

   - **Option 1: Erste Schritte** Wenn Sie **auf "Erste Schritte"** klicken, erhalten Sie eine reihe von Fragen mit relevanten Auswahlen, um die Kriterien zu definieren. Nachdem Sie den ersten Abschnitt **"Erste** Schritte" abgeschlossen haben, fahren Sie mit **"Websites** entwerfen" fort, um Ihre Websitearchitektur zu definieren. Fahren Sie mit Schritt 3 fort, um diese Option zu vervollständigen.

   - **Option 2: Entwerfen von Websites** Wenn Sie **auf der Willkommensseite** auf "Websites entwerfen" klicken, werden die Fragen im Abschnitt **"Erste** Schritte" umgeht. Die Informationen, die durch Antworten auf die Fragen  im Abschnitt "Erste Schritte" gesammelt worden wären, werden mit dieser Option auf Standardwerte festgelegt. Durch Klicken auf **"Websites entwerfen"** kann der erfahrene Designer das erste Gespräch umgehen und die Standardwerte bei Bedarf auf der Startseite der zentralen **Standorte** ändern. Um diese Option zu vervollständigen, überspringen Sie die Schritte 3 bis 5, und beginnen Sie mit Schritt 6.

   - **Option 3: Anzeigen der gespeicherten Topologie** Wenn Sie eine Topologie bereits durch vorherige Verwendung des Planungstools abgeschlossen und gespeichert haben, können Sie die meisten dieser Schritte überspringen und mit dem Öffnen und Anzeigen der Topologie beginnen. Sie können auch Änderungen und Aktualisierungen an der Topologie vornehmen, sie erneut speichern und dann nach Microsoft Excel oder Microsoft Visio exportieren. Um diese Option zu vervollständigen, überspringen Sie die Schritte 3 bis 12, und beginnen Sie mit Schritt 13.

3. Klicken **Sie auf "Erste Schritte",** um mit dem Entwerfen Ihrer Skype for Business Server 2015-Topologie zu beginnen.

4. Beantworten Sie jeden Abschnitt, indem Sie die entsprechenden  Kriterien für Ihren Entwurf auswählen, und klicken Sie dann auf "Weiter", um mit der nächsten Assistentenseite fortzufahren. Klicken **Sie auf "Zurück",** um Änderungen auf vorherigen Seiten vorzunehmen.

    > [!TIP]
    > Jede Seite enthält eine Beschreibung der Auswahlkriterien und Empfehlungen basierend auf bevorzugten Methoden und der Kapazitätsplanung. Wenn Sie zusätzliche Details  benötigen, klicken Sie auf "Weitere Informationen", um detaillierte Informationen aus der Planungsdokumentation für Skype for Business Server 2015 auf der Website von Microsoft zu erhalten. Sie müssen über eine Internetverbindung verfügen, um auf die Microsoft-Website zugreifen zu können.

5. Wählen Sie die entsprechenden Optionen für Ihr Design aus. Nachdem die anfänglichen Kriterien definiert wurden, wird auf einer Seite bestätigt, dass die Übersicht über die Features vollständig ist.

6. Klicken **Sie auf "Standorte entwerfen",** um ihren zentralen Standort zu definieren.

    > [!NOTE]
    > Jede Skype for Business Server 2015-Topologie hat mindestens einen zentralen Standort. Ihr Entwurf kann einen zentralen Standort, einen zentralen Standort mit einer Reihe von Zweigstellenstandorten, eine Reihe von zentralen Standorten oder eine Reihe von zentralen Standorten mit Zweigstellenstandorten haben, die jedem zentralen Standort zugeordnet sind.

7. Geben **Sie im Standortnamen** den Namen ein, der diesen zentralen Standort identifiziert.

8. Geben **Sie unter**"Benutzer von Standort" die erwartete Anzahl gleichzeitiger Benutzer ein, die an diesem zentralen Standort zu hause sein werden.

9. Geben **Sie in "Cloud-homed Users"** die erwartete Anzahl gleichzeitiger Onlinebenutzer ein, die an diesem zentralen Standort zu hause sein werden.

10. Ändern Sie bei Bedarf die Auswahl für Onlinezusammenarbeit, Benutzer, Sprache, zusätzliche Bereitstellungsoptionen oder Serveranwendungen.

    > [!IMPORTANT]
    > An diesem Punkt im Entwurf können Sie nur Optionen für Ihre Bereitstellung auswählen oder löschen. Sie können jedoch in einer späteren Phase des Planungstools weitere Optionen konfigurieren. Es gibt auch Optionen, die nicht verfügbar sind und nicht geräumt werden können. Darüber hinaus müssen Sie möglicherweise eine Option deaktivieren, um eine andere zu löschen. Wenn Sie beispielsweise die Option **Enterprise-VoIP** unter "Voice" deaktivieren, werden  auch die Optionen "Reaktionsgruppe", "Ansage" und "Anruf parken" unter "Serveranwendungen" (alle sind Features von Enterprise-VoIP) ebenfalls entfernt.

11. Klicken Sie nach dem Definieren eines Websitenamens und der Anzahl der Benutzer auf **"Weiter".**

12. Auf den folgenden Seiten werden Informationen zu SIP-Domänen, Konferenzeinstellungen, Spracheinstellungen und Infrastruktur, Exchange UM, externem Benutzerzugriff, Einstellungen für beständigen Chat, Clienteinstellungen, Kollokationsoptionen und Zweigstellenstandorten angezeigt. Beantworten Sie diese Fragen entsprechend.

13. Die letzte Frage stellt sich, ob Sie einen weiteren zentralen Standort erstellen möchten. Wenn Sie **"Ja"** auswählen, kehrt das Planungstool zur Seite "Zentrale Standorte" zurück. Wenn Sie **"Nein"** auswählen, klicken  Sie auf **"Weiter",** und klicken Sie dann auf "Zeichnen", um die globale Topologieansicht auf hoher Ebene anzeigen zu können.

14. Klicken Sie auf "Anzeigen", um eine vorhandene **Topologie anzeigen zu können.**

15. Klicken Sie auf die XML-Datei, die die zuvor gespeicherte Topologie darstellt, und klicken Sie dann auf **Öffnen**.

16. Das Planungstool zeigt die Seite "Globale Topologie" an. Sie können nun mit dem Bearbeiten, Aktualisieren oder Ändern der Topologie beginnen, indem Sie die im Planungstool verfügbaren Tools verwenden.

## <a name="see-also"></a>Siehe auch

[Bearbeiten des Entwurfs](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
