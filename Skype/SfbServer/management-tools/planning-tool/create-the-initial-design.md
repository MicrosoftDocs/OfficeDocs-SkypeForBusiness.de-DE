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
description: Nachdem Sie das Skype for Business Server Planning Tool installiert haben, können Sie mit dem Planungstool beginnen und mit dem Entwerfen der vorgeschlagenen Skype for Business Server 2015-Infrastruktur beginnen.
ms.openlocfilehash: 756c59ce0598af186a5cedabe250f7f1e7ec323c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098681"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>Erstellen des anfänglichen Topologieentwurfs für Skype for Business Server 2015

Nachdem Sie das Skype for Business Server Planning Tool installiert haben, können Sie mit dem Planungstool beginnen und mit dem Entwerfen der vorgeschlagenen Skype for Business Server 2015-Infrastruktur beginnen.

> [!NOTE]
>  Das Planungstool ist ein assistentengesteuertes Tool mit detaillierten Anleitungen, um Ihre Entscheidungsfindung beim Entwerfen Ihrer Websites und Topologie zu informieren. Dieses Thema ist nicht als umfassendes Handbuch gedacht, sondern dient lediglich dazu, Sie mit der Verwendung des Planungstools in Ihren Entwurfssitzungen zu beginnen.

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>So beginnen Sie mit dem Planungstool, und erstellen Sie den ursprünglichen Entwurf

1. Starten Sie das Skype for Business Server 2015-Planungstool: Klicken Sie auf **Start,** klicken Sie auf **Alle** Programme, klicken Sie **auf Skype for Business Server 2015,** und klicken Sie dann auf **Planungstool**.

2. Nachdem das Planungstool gestartet wurde, wird die Seite **Willkommen beim Planungstool für Skype for Business Server 2015** angezeigt. Wählen Sie eine der folgenden Optionen aus, um Mit dem Entwurf zu beginnen:

   - **Option 1: Erste Schritte** Wenn Sie **auf Erste Schritte** klicken, finden Sie eine reihe von Interviewfragen mit relevanten Auswahlen, um die Kriterien zu definieren. Nachdem Sie den ersten Abschnitt **"Erste** Schritte" abgeschlossen haben, fahren Sie mit **Design Sites fort,** um Ihre Websitearchitektur zu definieren. Fahren Sie mit Schritt 3 fort, um diese Option zu vervollständigen.

   - **Option 2: Entwerfen von Websites** Wenn Sie **auf der** Willkommensseite auf Entwurfswebsites klicken, werden die Im Abschnitt Erste Schritte vorgestellten **Interviewfragen** umgeht. Die Informationen, die durch Antworten auf die Interviewfragen im Abschnitt **Erste** Schritte gesammelt worden wären, werden mit dieser Option auf Standardwerte festgelegt. Durch Klicken auf **Websites entwerfen** kann der erfahrene Designer das erste Interview umgehen und die Standardwerte bei Bedarf auf der Startseite der zentralen **Websites** ändern. Um diese Option zu vervollständigen, überspringen Sie die Schritte 3 bis 5, und beginnen Sie mit Schritt 6.

   - **Option 3: Anzeigen der gespeicherten Topologie** Wenn Sie eine Topologie bereits durch vorherige Verwendung des Planungstools abgeschlossen und gespeichert haben, können Sie die meisten dieser Schritte überspringen und mit dem Öffnen und Anzeigen der Topologie beginnen. Sie können auch Änderungen und Aktualisierungen an der Topologie vornehmen, sie erneut speichern und dann nach Microsoft Excel oder Microsoft Visio exportieren. Um diese Option zu vervollständigen, überspringen Sie die Schritte 3 bis 12, und beginnen Sie mit Schritt 13.

3. Klicken **Sie auf Erste** Schritte, um mit dem Entwerfen Ihrer Skype for Business Server 2015-Topologie zu beginnen.

4. Beantworten Sie jeden Abschnitt, indem Sie die entsprechenden Kriterien für Ihren Entwurf auswählen, und klicken Sie dann auf **Weiter,** um mit der nächsten Seite des Assistenten fortzufahren. Klicken **Sie auf Zurück,** um Änderungen an vorherigen Seiten vorzunehmen.

    > [!TIP]
    > Jede Seite enthält eine Beschreibung der Auswahlkriterien und Empfehlungen basierend auf bevorzugten Methoden und Kapazitätsplanung. Wenn Sie zusätzliche Details benötigen, klicken Sie auf **Weitere** Informationen, um detaillierte Informationen aus der Skype for Business Server 2015-Planungsdokumentation auf der Microsoft-Website zu lesen. Sie müssen über Eine Internetverbindung verfügen, um auf die Microsoft-Website zugreifen zu können.

5. Wählen Sie die entsprechenden Optionen für Ihren Entwurf aus. Nachdem die anfänglichen Kriterien definiert wurden, wird auf einer Seite bestätigt, dass die Übersicht über die Features abgeschlossen ist.

6. Klicken **Sie auf Websites entwerfen,** um Ihren zentralen Standort zu definieren.

    > [!NOTE]
    > Jede Skype for Business Server 2015-Topologie hat mindestens einen zentralen Standort. Ihr Entwurf kann einen zentralen Standort, einen zentralen Standort mit einer Reihe von Zweigstellenstandorten, eine Reihe von zentralen Standorten oder eine Reihe zentraler Standorte mit Zweigstellenstandorten haben, die jedem zentralen Standort zugeordnet sind.

7. Geben **Sie unter Websitename** den Namen ein, der diesen zentralen Standort identifiziert.

8. Geben Sie unter Site **Homed Users** die erwartete Anzahl von lokalen gleichzeitigen Benutzern ein, die an diesem zentralen Standort heimgeheimt werden.

9. Geben **Sie in Cloud Homed Users** die erwartete Anzahl gleichzeitiger Onlinebenutzer ein, die an diesem zentralen Standort zu Hause sind.

10. Ändern Sie die Auswahl für Onlinezusammenarbeit, Benutzer, Voice, zusätzliche Bereitstellungsoptionen oder Serveranwendungen nach Bedarf.

    > [!IMPORTANT]
    > An dieser Stelle im Entwurf können Sie nur Optionen für Ihre Bereitstellung auswählen oder löschen. Sie können jedoch in einer späteren Phase des Planungstools weitere Optionen konfigurieren. Es gibt auch Optionen, die nicht verfügbar sind und nicht geräumt werden können. Darüber hinaus müssen Sie möglicherweise eine Option löschen, um eine andere zu löschen. Wenn Sie beispielsweise die Option **Enterprise-VoIP** unter Voice deaktivieren, werden auch die Optionen Reaktionsgruppe, Ansage und **Anrufparken** unter Serveranwendungen (alle sind Features von Enterprise-VoIP) entfernt.

11. Klicken Sie nach dem Definieren eines Websitenamens und der Anzahl der Benutzer auf **Weiter**.

12. Auf den folgenden Seiten finden Sie Informationen zu SIP-Domänen, Konferenzeinstellungen, Spracheinstellungen und Infrastruktur, Exchange UM, externen Benutzerzugriff, Einstellungen für beständigen Chat, Clienteinstellungen, Kollokationsoptionen und Zweigstellenstandorten. Beantworten Sie diese Fragen gegebenenfalls.

13. Die letzte Frage lautet, ob Sie einen anderen zentralen Standort erstellen möchten. Wenn Sie Ja **auswählen,** kehrt das Planungstool zur Seite Zentrale Websites zurück. Wenn Sie Nein **auswählen,** klicken Sie  auf **Weiter**, und klicken Sie dann auf Zeichnen, um die globale Topologieansicht auf hoher Ebene anzeigen zu können.

14. Klicken Sie zum Anzeigen einer vorhandenen Topologie auf **Anzeigen**.

15. Klicken Sie auf die XML-Datei, die die zuvor gespeicherte Topologie darstellt, und klicken Sie dann auf **Öffnen**.

16. Das Planungstool zeigt die Seite Globale Topologie an. Sie können nun mit der Bearbeitung, Aktualisierung oder Änderung der Topologie beginnen, indem Sie die im Planungstool verfügbaren Tools verwenden.

## <a name="see-also"></a>Siehe auch

[Bearbeiten des Entwurfs](/previous-versions/office/lync-server-2013/lync-server-2013-editing-the-design)