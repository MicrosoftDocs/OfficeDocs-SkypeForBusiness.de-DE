---
title: Einrichten von Feiertagen in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
description: Informationen Sie zum Einrichten von Feiertagen in der Microsoft-Teams, und schließen Sie sie an die automatische Telefonzentrale.
ms.openlocfilehash: 72feed025e43eb7242f75608534db45d74aca9c9
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517119"
---
# <a name="set-up-holidays-in-microsoft-teams"></a>Einrichten von Feiertagen in Microsoft Teams

Sie können das Feature Microsoft Teams Feiertage verwenden, um bestimmte Termine planen und wie oft Wenn Personen in Ihrer Organisation Zeit aus deaktiviert und werden arbeiten und während der normalen Geschäftszeiten nicht verfügbar. 

Sie können die Feiertage mit automatischen Telefonzentralen verknüpfen, die Sie in Ihrer Organisation zu erstellen. Automatische Telefonzentralen können Anrufer navigieren ein Menüsystem zum Abrufen von an die richtige Abteilung oder auf die benötigten Informationen abrufen. Beim Konfigurieren von Feiertag Anruf Einstellungen für eine automatische Telefonzentrale können Sie wählen Sie den Feiertag aus einer Liste, eine Begrüßung hinzufügen, und geben mithilfe des Aufrufs Aktionen, wenn es von der automatischen Telefonzentrale während des Feiertags entgegengenommen wurde.

Ein gutes Beispiel erstellt einen Feiertag für Weihnachten für Wenn viele Ihre Mitarbeiter nicht im Büro sind. Nach dem Erstellen des Feiertags und legen Sie fest, würden Sie das Hauptfenster von den Feiertag hinzufügen automatische Telefonzentrale, sodass Wenn Personen anrufen, werden sie eine audio-Nachricht hören, den, die Sie erstellt haben. Etwa, "Wir sind für Weihnachten aus 22. Dezember bis 27. Dezember geschlossen. Lassen Sie uns eine Sprachnachricht deshalb wir den Anruf zurück können, wenn wir wieder im Büro sind."

Weitere Informationen zu automatischen Telefonzentralen finden Sie unter [Was sind Telefonsystem automatischen Telefonzentralen](what-are-phone-system-auto-attendants.md)?  

## <a name="create-a-holiday"></a>Erstellen Sie einen Feiertag

1. Wechseln Sie in der Microsoft-Teams-Verwaltungskonsole zu **Org geltende Einstellungen** > **Feiertage**.

2. Wählen Sie **neuen Feiertag**aus.

3. Geben Sie einen Namen des Feiertags ein.

4. Wählen Sie **Neues Datum hinzufügen**.

5. Wählen Sie unter **Startzeit**das Kalendersymbol, und wählen Sie das Datum des Feiertags beginnen sollen.

6. Verwenden Sie die Dropdown-Liste, um eine Startzeit des Feiertags auszuwählen.

7. Wählen Sie unter **Endzeit**das Kalendersymbol, und wählen Sie das Datum für das Ende des Feiertags werden sollen. Wenn Feiertags nur ein Tag ist, sollte dies das gleiche Datum wie der Datenbankserver unter **Startzeit**gewählte.

8. Verwenden Sie die Dropdown-Liste, um eine Endzeit für den Feiertag auszuwählen.

9. Wählen Sie **Speichern**aus.

## <a name="change-a-holiday"></a>Ändern Sie einen Feiertag

1. Wechseln Sie in der Microsoft-Teams-Verwaltungskonsole zu **Org geltende Einstellungen** > **Feiertage**.

2. Wählen Sie den Feiertag aus der Liste aus.

3. Wählen Sie unter **Startzeit**das Kalendersymbol, und wählen Sie das Datum des Feiertags beginnen sollen.

4. Verwenden Sie die Dropdown-Liste, um eine Startzeit des Feiertags auszuwählen.

5. Wählen Sie unter **Endzeit**das Kalendersymbol, und wählen Sie das Datum für das Ende des Feiertags werden sollen. 

6. Verwenden Sie die Dropdown-Liste, um eine Endzeit für den Feiertag auszuwählen.

7. Wählen Sie **Speichern**aus.

## <a name="connect-a-holiday-to-an-auto-attendant"></a>Verbinden Sie einen Feiertag an eine automatische Telefonzentrale

1. Wechseln Sie in der Microsoft-Teams-Verwaltungskonsole zu **VoIP** > **Telefonzentralen**.
2. Wählen Sie eine Ressourcenkonto aus der Liste aus.
3. Wählen Sie im linken Bereich **Feiertag Einstellungen für die**.
4. Wählen Sie **neuen Feiertag**aus.
5. Wählen Sie den Feiertag aus der Dropdownliste aus.
6. Sie können eine optionale Begrüßung hinzufügen:
    - Um eine aufgezeichnete Ansage wiedergegeben werden sollen, wählen Sie **eine Audiodatei wiedergeben**, und wählen Sie dann auf **Datei hochladen**. Navigieren Sie zum Speicherort der Audiodatei, wählen Sie die Datei, und wählen Sie dann auf **Öffnen**.
    - Um eine Begrüßung zu erstellen, wählen Sie **eine Nachricht Begrüßung**, und geben Sie Ihre Nachricht. Anrufer hören diese Nachricht, wenn Sie eine Audiodatei noch nicht bereitgestellt haben.
7. Wählen Sie **Trennen**, um den Anruf zu beenden, nachdem die Ansage, klicken Sie unter **Aktionen**. 

    Um den Anruf umleiten, wählen Sie **Umleiten von Anrufen**, und wählen Sie dann die Person, die den umgeleiteten Anruf aus dem Dropdown-Listenfeld oder die Person Suchen nach Anzeigename entgegennimmt.
8. Wählen Sie **Speichern**aus.

## <a name="related-topics"></a>Verwandte Themen

[Was sind automatische Telefonzentralen Telefonsystem](what-are-phone-system-auto-attendants.md)?