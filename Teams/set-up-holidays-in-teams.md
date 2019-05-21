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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
description: Hier erfahren Sie, wie Sie Feiertage in Microsoft Teams einrichten und mit der automatischen Telefonzentrale verbinden.
ms.openlocfilehash: bf11fbed270d930ece29cdd89af053c34bc606da
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298702"
---
# <a name="set-up-holidays-in-microsoft-teams"></a>Einrichten von Feiertagen in Microsoft Teams

Sie können die Microsoft Teams Holidays-Funktion verwenden, um bestimmte Datums-und Uhrzeitangaben zu planen, in denen Personen in Ihrer Organisation Zeit für die Arbeit frei nehmen und während regulärer Geschäftszeiten nicht zur Verfügung stehen. 

Sie können die Feiertage mit automatischen Telefonzentralen verknüpfen, die Sie in Ihrer Organisation erstellen. Mit automatischen Telefonzentralen können Anrufer in einem Menü System navigieren, um zur richtigen Abteilung zu gelangen oder um Informationen zu erhalten, die Sie benötigen. Wenn Sie die Einstellungen für den Feiertags Anruf für eine automatische Telefonzentrale konfigurieren, können Sie den Feiertag aus einer Liste auswählen, eine Begrüßung hinzufügen und angeben, was mit dem Anruf zu tun ist, wenn er von der automatischen Telefonzentrale während des Urlaubs beantwortet wird.

Ein gutes Beispiel ist das Erstellen eines weihnachtsfeiertags, wenn viele ihrer Mitarbeiter nicht am Arbeitsplatz sind. Nachdem Sie das Feiertags-und festgelegte Uhrzeiten erstellt haben, fügen Sie den Feiertag Ihrer Haupt-Telefonzentrale hinzu, damit die Personen, die Sie angerufen haben, eine von Ihnen erstellte Audionachricht hören. So etwas wie: "Wir sind für Weihnachten vom 22. Dezember bis 27. Dezember geschlossen. Bitte geben Sie uns eine Sprachnachricht, damit wir Ihren Anruf zurückgeben können, wenn wir wieder im Büro sind. "

Weitere Informationen zu automatischen Telefonzentralen finden Sie unter [Was sind automatische Cloud-Telefonzentralen](what-are-phone-system-auto-attendants.md)?  

## <a name="create-a-holiday"></a>Erstellen eines Feiertags

1. Wechseln Sie im Microsoft Teams Admin Center zu den **organisationsweiten Einstellungen** > **Feiertage**.

2. Wählen Sie **neue Feiertage**aus.

3. Geben Sie einen Namen für den Feiertag ein.

4. Wählen Sie **Neues Datum hinzufügen**aus.

5. Wählen Sie unter **Startzeit**das Kalendersymbol aus, und wählen Sie das Datum aus, an dem der Feiertag beginnen soll.

6. Verwenden Sie die Dropdownliste, um eine Startzeit für den Feiertag auszuwählen.

7. Wählen Sie unter **Endzeit**das Kalendersymbol aus, und wählen Sie das Datum aus, an dem der Feiertag enden soll. Wenn es sich bei dem Feiertag nur um einen Tag handelt, sollte dies derselbe Termin sein, den Sie unter **Startzeit**gewählt haben.

8. Verwenden Sie die Dropdownliste, um eine Endzeit für den Feiertag auszuwählen.

9. Wählen Sie **Speichern**aus.

## <a name="change-a-holiday"></a>Ändern eines Feiertags

1. Wechseln Sie im Microsoft Teams Admin Center zu den **organisationsweiten Einstellungen** > **Feiertage**.

2. Wählen Sie den Feiertag in der Liste aus.

3. Wählen Sie unter **Startzeit**das Kalendersymbol aus, und wählen Sie das Datum aus, an dem der Feiertag beginnen soll.

4. Verwenden Sie die Dropdownliste, um eine Startzeit für den Feiertag auszuwählen.

5. Wählen Sie unter **Endzeit**das Kalendersymbol aus, und wählen Sie das Datum aus, an dem der Feiertag enden soll. 

6. Verwenden Sie die Dropdownliste, um eine Endzeit für den Feiertag auszuwählen.

7. Wählen Sie **Speichern**aus.

## <a name="connect-a-holiday-to-an-auto-attendant"></a>Verbinden eines Feiertags mit einer automatischen Telefonzentrale

1. Wechseln Sie im Microsoft Teams Admin Center zu **VoIP** > -**Telefonzentralen**.
2. Wählen Sie ein Ressourcenkonto in der Liste aus.
3. Wählen Sie im linken Bereich **Feiertags Anrufeinstellungen**aus.
4. Wählen Sie **neue Feiertage**aus.
5. Wählen Sie den Feiertag in der Dropdown-Liste aus.
6. Sie können eine optionale Begrüßung hinzufügen:
    - Wenn Sie eine aufgezeichnete Ansage wiedergeben möchten, wählen Sie **Audiodatei wiedergeben**aus, und wählen Sie **Datei hochladen**aus. Navigieren Sie zum Speicherort der Audiodatei, wählen Sie die Datei aus, und wählen Sie dann **Öffnen**aus.
    - Wenn Sie eine Begrüßung erstellen möchten, wählen Sie **Grußnachricht eingeben**aus, und geben Sie dann Ihre Nachricht ein. Die Anrufer hören diese Nachricht, wenn Sie keine Audiodatei angegeben haben.
7. Wenn Sie den Anruf nach der Begrüßung beenden möchten, wählen Sie unter **Aktionen**die Option **trennen**aus. 

    Wenn Sie den Anruf umleiten möchten, wählen Sie **Anruf umleiten**aus, und wählen Sie dann die Person aus, die den umgeleiteten Anruf aus der Dropdown-Liste erhält, oder suchen Sie nach der Person mit dem Anzeigenamen.
8. Wählen Sie **Speichern**aus.

## <a name="related-topics"></a>Verwandte Themen

[Was sind automatische Cloud-Telefonzentralen](what-are-phone-system-auto-attendants.md)?