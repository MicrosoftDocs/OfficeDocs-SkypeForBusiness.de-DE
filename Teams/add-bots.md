---
title: Hinzufügen von Bots für private Chats und Kanäle in Microsoft Teams
author: LolaJacobsen, DamienDoumer
ms.author: lolaj, Damien
manager: serdars
ms.date: 12/05/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras
description: Hier erfahren Sie, wie Sie in Microsoft Teams Bots für private Chats und Kanäle hinzufügen, benutzerdefinierte Bots erstellen und Ihren eigenen Bot für private Chats querladen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6987c14973443e62f0be69f9872c4e248ddb026b
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548845"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>Hinzufügen von Bots für private Chats und Kanäle in Microsoft Teams
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Bots sind automatisierte Programme, die auf Abfragen antworten oder Updates und Benachrichtigungen zu Details herausgeben, die Benutzer interessant finden oder über die sie auf dem Laufenden bleiben möchten. Mithilfe von Bots können Benutzer über Chat Unterhaltungen in Microsoft Teams mit Cloud-Diensten wie Aufgabenverwaltung,-Planung und-Polling interagieren. Bots für Microsoft Teams sind auf dem [Microsoft bot-Framework](https://go.microsoft.com/fwlink/?linkid=854370)aufgebaut. Die Bots, die mithilfe dieses Frameworks entwickelt wurden, können problemlos für Microsoft Teams aktiviert werden. Weitere Informationen finden Sie unter [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md).

Zurzeit unterstützt Microsoft Teams Bots in privaten Chats und in Kanälen in einem Team. Administratoren können steuern, ob die Verwendung von Bots innerhalb des Office 365-Mandanten zulässig oder untersagt ist.<span id="_T-Bot" class="anchor"></span>

In Microsoft Teams können Bots genutzt werden, die von der Community entwickelt wurden. Die Funktionen des Bots und das Querladen von Bots müssen auf Mandantenebene aktiviert werden, damit benutzerdefinierte Bots funktionieren. Bots können in privaten Chats oder in Kanälen verwendet werden. Für Kanäle können Teambesitzer oder -mitglieder Bots hinzufügen.

Weitere Informationen finden Sie unter [Apps und Dienste](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) im Abschnitt „Verwenden von Bots“. 

> [!IMPORTANT]
> Das Hinzufügen eines bot von GUID zu anderen als Testzwecken wird nicht empfohlen. Dadurch wird die Funktionalität eines bot stark eingeschränkt. Bots in der Produktions Nutzung sollten als Teil einer APP zu Teams hinzugefügt werden. Weitere Informationen finden Sie unter [Erstellen eines bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create) und [Testen und Debuggen Ihres Microsoft Teams-bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)

<a name="create-custom-bots-for-microsoft-teams"></a>Erstellen von benutzerdefinierten Bots für Microsoft Teams
--------------------------------------

Mit Microsoft Bot Framework können Sie leicht einen Bot erstellen, der in Ihre Branchenanwendungen integriert werden kann. Im Leitfaden zum [Erstellen und Testen eines Bots für Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) erfahren Sie, wie Sie Ihre eigenen Bots entwickeln und veröffentlichen können.

Wenn Sie einen Bot erstellen und in Bot Framework registrieren, können Sie wählen, ob er veröffentlicht werden soll. Wenn Sie den Bot nicht veröffentlichen, bleibt er privat. Sie können auch festlegen, dass sich die Benutzer vor der Verwendung des Bots anmelden müssen. Dadurch stellen Sie sicher, dass nur Mitarbeiter Ihrer Organisation auf den Bot zugreifen können, selbst wenn die Anwendungs-ID des Bots bekannt ist. Ein [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372)-Codebeispiel auf GitHub zeigt, wie Sie mithilfe von Bots Benutzer gegenüber Active Directory authentifizieren.

Bots können mit dem [Bot Framework-Emulator](https://go.microsoft.com/fwlink/?linkid=854373) getestet werden, bevor sie für Ihre Teams bereitgestellt werden.

<a name="side-load-your-own-bot-for-private-chat"></a>Querladen Ihres eigenen Bots für private Chats
---------------------------------------

1. Nachdem Sie Ihren bot erstellt haben, wechseln Sie zu den **Anwendungseinstellungen** für den von Ihnen entwickelten bot, und kopieren Sie dann unter **App-Einstellungen**den Wert der **MicrosoftAppId** -Einstellung. ![Screenshot der Seite "Anwendungseinstellungen" für einen bot](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)



2.  Wählen Sie in Microsoft Teams im Bereich **Chat** das **Symbol zum Hinzufügen eines Chats** aus. Fügen Sie in **An:** die **Microsoft-App-ID** Ihres Bots ein. ![Screenshot eines Chat Bereichs mit hervorgehobener Microsoft-App-ID](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)



3.  Die App-ID wird in den **Botnamen** aufgelöst. Dann können Sie eine Chatunterhaltung mit dem Bot beginnen.

<a name="side-load-your-bot-for-channels"></a>Seite laden Sie Ihren bot für Kanäle
-----------------------------------

Wenn Sie Ihren bot für Ihre Kollegen freigeben möchten, gehen Sie wie folgt vor, um Sie zu Kanälen in verschiedenen Teams hinzuzufügen:

1. Nachdem Sie [ein App-Paket für Ihren bot erstellt](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)haben, öffnen Sie Teams, und navigieren Sie zu dem Team, in dem Sie den bot laden können.
2. Fügen Sie **[App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, APP zu Microsoft Teams hinzu.
3. Wählen Sie in App Studio die Registerkarte **Manifest-Editor** aus. ![Screenshot der Registerkarte Manifest-Editor.](media/Adding_Bot_To_Teams.png)
4. Wenn Sie Ihren bot hinzufügen möchten, wählen Sie bot und dann einen vorhandenen bot hinzufügen aus, dann haben Sie die Möglichkeit, einen vorhandenen bot aus einem Dropdown-Menü zu wählen oder die ID eines Ihrer vorhandenen Bots einzugeben.
![Zeigt die Auswahl des bereits erstellten bot an.](media/Select_Existing_Bot.png)
5. Navigieren Sie zum Speicherort des App-Pakets, wählen Sie es aus, und klicken Sie dann auf **Öffnen**.
6. Wählen Sie den Namen Ihres bot aus (vergessen Sie nicht, das Kontrollkästchen "Team" im Abschnitt "Bereich" zu aktivieren).
7. Wählen Sie die Option testen und verteilen aus.
8. Wählen Sie im Dialogfeld, das eingeblendet wird, das Team aus, mit dem Sie Ihren bot verbinden möchten.

Damit steht Ihr bot im Team Ihres Microsoft Teams zur Verfügung.
