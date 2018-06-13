---
title: Hinzufügen von Bots für private Chats und Kanäle in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: lucarras
description: Hier erfahren Sie, wie Sie in Microsoft Teams Bots für private Chats und Kanäle hinzufügen, benutzerdefinierte Bots erstellen und Ihren eigenen Bot für private Chats querladen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08417f4aafae8c7fd844cb253a889b833d0e6266
ms.sourcegitcommit: c05731b8a757864c0f6620bfeda3ae28a3582011
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2018
ms.locfileid: "19856028"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>Hinzufügen von Bots für private Chats und Kanäle in Microsoft Teams
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Bots sind automatisierte Programme, die Antworten auf Abfragen oder übergeben von Updates und Benachrichtigungen über Details Benutzer interessante oder möchten, zu dem Laufenden zu bleiben. Bots Benutzern die Interaktion mit Clouddiensten wie vorgangsverwaltung, Planung und Abrufe, über Chat Unterhaltungen in Microsoft-Teams. Bots für Microsoft-Teams, basieren auf dem [Microsoft Bot-Framework](https://go.microsoft.com/fwlink/?linkid=854370). Die Bots, die mithilfe dieses Frameworks entwickelt werden kann auf einfache Weise für Microsoft-Teams, aktiviert werden. Weitere Informationen finden Sie unter [Microsoft-Teams, Verwalten von Features in Office 365-Organisation](enable-features-office-365.md).

Zurzeit unterstützt Microsoft Teams Bots in privaten Chats und in Kanälen in einem Team. Administratoren können steuern, ob die Verwendung von Bots innerhalb des Office 365-Mandanten zulässig oder untersagt ist.<span id="_T-Bot" class="anchor"></span>

In Microsoft Teams können Bots genutzt werden, die von der Community entwickelt wurden. Die Funktionen des Bots und das Querladen von Bots müssen auf Mandantenebene aktiviert werden, damit benutzerdefinierte Bots funktionieren. Bots können in privaten Chats oder in Kanälen verwendet werden. Für Kanäle können Teambesitzer oder -mitglieder Bots hinzufügen.

Weitere Informationen finden Sie unter [Apps und Dienste](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) im Abschnitt „Verwenden von Bots“. 




<a name="create-custom-bots-for-microsoft-teams"></a>Erstellen von benutzerdefinierten Bots für Microsoft Teams
--------------------------------------

Mit Microsoft Bot Framework können Sie leicht einen Bot erstellen, der in Ihre Branchenanwendungen integriert werden kann. Im Leitfaden zum [Erstellen und Testen eines Bots für Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) erfahren Sie, wie Sie Ihre eigenen Bots entwickeln und veröffentlichen können.

Wenn Sie einen Bot erstellen und in Bot Framework registrieren, können Sie wählen, ob er veröffentlicht werden soll. Wenn Sie den Bot nicht veröffentlichen, bleibt er privat. Sie können auch festlegen, dass sich die Benutzer vor der Verwendung des Bots anmelden müssen. Dadurch stellen Sie sicher, dass nur Mitarbeiter Ihrer Organisation auf den Bot zugreifen können, selbst wenn die Anwendungs-ID des Bots bekannt ist. Ein [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372)-Codebeispiel auf GitHub zeigt, wie Sie mithilfe von Bots Benutzer gegenüber Active Directory authentifizieren.

Bots können mit dem [Bot Framework-Emulator](https://go.microsoft.com/fwlink/?linkid=854373) getestet werden, bevor sie für Ihre Teams bereitgestellt werden.

<a name="side-load-your-own-bot-for-private-chat"></a>Querladen Ihres eigenen Bots für private Chats
---------------------------------------

1. Nachdem Sie Ihre Bot erstellt haben, wechseln Sie an den **Einstellungen** für den Robot, das, die Sie, klicken Sie dann unter **App-Einstellungen**entwickelt, kopieren Sie den Wert der Einstellung **MicrosoftAppId** . ![Screenshot der Seite Einstellungen für für ein Bot mit Microsoft App-ID hervorgehoben.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)



2.  Wählen Sie in Microsoft Teams im Bereich **Chat** das **Symbol zum Hinzufügen eines Chats** aus. Fügen Sie in **An:** die **Microsoft-App-ID** Ihres Bots ein. ![Screenshot eines Chatbereichs mit dem hervorgehobenen Symbol zum Hinzufügen eines Chats und der hervorgehobenen Zeile „An“ mit der Microsoft-App-ID](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)



3.  Die App-ID wird in den **Botnamen** aufgelöst. Dann können Sie eine Chatunterhaltung mit dem Bot beginnen.
