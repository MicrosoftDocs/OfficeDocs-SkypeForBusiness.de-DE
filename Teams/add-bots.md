---
title: "Hinzufügen von Bots für private Chats und Kanäle in Microsoft Teams | Microsoft-Support"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Hier erfahren Sie, wie Sie in Microsoft Teams Bots für private Chats und Kanäle hinzufügen, benutzerdefinierte Bots erstellen und Ihren eigenen Bot für private Chats querladen."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 905a105fba269aebb2b01cbccc1a47e7667ca341
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2017
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>Hinzufügen von Bots für private Chats und Kanäle in Microsoft Teams
==========================================================

Bots sind automatisierte Programme, die so eingerichtet sind, dass sie auf Abfragen reagieren oder Updates und Benachrichtigungen zu Details bereitstellen, für die Benutzer sich interessieren oder über die sie stets informiert sein möchten. Über Bots können Benutzer durch Chatunterhaltungen in Microsoft Teams mit Clouddiensten wie Aufgabenverwaltung, Planung und Umfragen interagieren. Bots für Microsoft Teams basieren auf [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370), und die mit diesem Framework entwickelten Bots können leicht für Microsoft Teams aktiviert werden.

Zurzeit unterstützt Microsoft Teams Bots in privaten Chats und in Kanälen in einem Team. Administratoren können steuern, ob die Verwendung von Bots innerhalb des Office 365-Mandanten zulässig oder untersagt ist.<span id="_T-Bot" class="anchor"></span>

In Microsoft Teams können Bots genutzt werden, die von der Community entwickelt und verfügbar gemacht wurden. Die Funktionen des Bots und das Querladen von Bots müssen auf Mandantenebene aktiviert werden, damit benutzerdefinierte Bots funktionieren. Bots können in privaten Chats oder in Kanälen verwendet werden. Für Kanäle können Teambesitzer oder -mitglieder Bots hinzufügen.

<a name="add-bots-for-private-chat-and-channels"></a>Hinzufügen von Bots für private Chats und Kanäle
--------------------------------------

Es gibt zwei Möglichkeiten, einen Bot für private Chats und Kanäle zu integrieren:

1.  Installieren Sie öffentlich verfügbare Bots für **private Chats** oder für **Kanäle**. (Das ist die erste Option.)

2.  Alternativ können Sie Bots suchen, indem Sie zu **Chat** navigieren, nach einem **Kontakt** suchen und dann auf **Apps entdecken** klicken.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image1.png)

3.  Wählen Sie wie unten gezeigt aus, mit welchem **Bot** Sie eine Unterhaltung führen möchten.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image2.png)

4.  Erteilen Sie dem ausgewählten Bot **Berechtigungen**, und wählen Sie aus, ob Sie **Bots in einem privaten Chat** verwenden möchten, oder wählen Sie ein **Team** aus, in dem Sie den Bot verwenden möchten.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image3.png)

5.  Alternativ können Sie einen Bot in einem Kanal eines Teams verwenden, indem Sie einfach auf **View Team and Bots** (Team und Bots anzeigen) klicken. Hier können Sie weitere Bots entdecken.

6.  Ein Bot kann jederzeit aus dem Team entfernt werden. Klicken Sie einfach auf **View Team and Bots** (Team und Bots anzeigen), um alle Bots zu sehen, und **entfernen** Sie dann den gewünschten Bot.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image4.png)

<a name="create-custom-bots-for-microsoft-teams"></a>Erstellen von benutzerdefinierten Bots für Microsoft Teams
--------------------------------------

Mit Microsoft Bot Framework können Sie leicht einen Bot erstellen, der in Ihre Branchenanwendungen integriert werden kann. Im Leitfaden zum [Erstellen und Testen eines Bots für Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) erfahren Sie, wie Sie Ihre eigenen Bots entwickeln und veröffentlichen können.

Wenn Sie einen Bot erstellen und in Bot Framework registrieren, können Sie wählen, ob er veröffentlicht werden soll. Wenn Sie den Bot nicht veröffentlichen, bleibt er privat. Sie können auch festlegen, dass sich die Benutzer vor der Verwendung des Bots anmelden müssen. Dadurch stellen Sie sicher, dass nur Mitarbeiter Ihrer Organisation auf den Bot zugreifen können, selbst wenn die Anwendungs-ID des Bots bekannt ist. Ein [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372)-Codebeispiel auf GitHub zeigt, wie Sie mithilfe von Bots Benutzer gegenüber Active Directory authentifizieren.

Bots können mit dem [Bot Framework-Emulator](https://go.microsoft.com/fwlink/?linkid=854373) getestet werden, bevor sie für Ihre Teams bereitgestellt werden.

<a name="side-load-your-own-bot-for-private-chat"></a>Querladen Ihres eigenen Bots für private Chats
---------------------------------------

1.  Wenn Sie Ihren Bot erstellt haben, navigieren Sie zur **Botdashboard**-[Seite](https://go.microsoft.com/fwlink/?linkid=854374) für den entwickelten Bot, und kopieren Sie unter **Details** die **Microsoft-App-ID**.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  Wählen Sie in Microsoft Teams im Bereich **Chat** das **Symbol zum Hinzufügen eines Chats** aus. Fügen Sie in **An:** die **Microsoft-App-ID** Ihres Bots ein.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3.  Die App-ID wird in den **Botnamen** aufgelöst. Dann können Sie eine Chatunterhaltung mit dem Bot beginnen.
