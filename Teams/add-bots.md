---
title: Hinzufügen von Bots für private Chats und Kanäle in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras, jakon
description: Erfahren Sie, wie Sie Bots in Microsoft Teams für persönliche Chats, Gruppen-Chats und Kanäle hinzufügen und ihre eigenen Bots für persönliche Chats, Gruppen-Chats und Kanäle Hochladen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f5f031b01837980897f2c1f8ad5d306e056257b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239057"
---
<a name="add-bots-for-personal-chats-group-chats-and-channels-in-microsoft-teams"></a>Hinzufügen von Bots für persönliche Chats, Gruppen-Chats und Kanäle in Microsoft Teams
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Bots sind automatisierte Programme, die auf Abfragen antworten oder Updates und Benachrichtigungen zu Details herausgeben, die Benutzer interessant finden oder über die sie auf dem Laufenden bleiben möchten. Mithilfe von Bots können Benutzer über Chat Unterhaltungen in Microsoft Teams mit Cloud-Diensten wie Aufgabenverwaltung,-Planung und-Polling interagieren. Bots für Teams sind auf dem [Microsoft bot-Framework](https://go.microsoft.com/fwlink/?linkid=854370)aufgebaut. Die Bots, die mithilfe dieses Frameworks entwickelt wurden, können für Teams problemlos aktiviert werden. Weitere Informationen finden Sie unter [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md).

Derzeit unterstützt Teams Bots in persönlichen Chats, Gruppen-Chats und Kanälen innerhalb eines Teams. Administratoren können steuern, ob die Verwendung von Bots innerhalb des Office 365-Mandanten zulässig oder verboten ist.<span id="_T-Bot" class="anchor"></span>

Bots, die von der Community entwickelt wurden, können innerhalb von Teams genutzt werden. Die Funktionalität des bot und die Möglichkeit zum Hochladen benutzerdefinierter Apps (auch bekannt als Sideloading) müssen auf Mandantenebene aktiviert sein, damit benutzerdefinierte Bots funktionsfähig sind. Bots können in persönlichen Chats, Gruppen-Chats und Kanälen verwendet werden. Für Kanäle können Teambesitzer oder -mitglieder Bots hinzufügen.

Weitere Informationen finden Sie unter [apps und Dienste](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).

> [!IMPORTANT]
> Das Hinzufügen eines bot von GUID zu anderen als Testzwecken wird nicht empfohlen. Dadurch wird die Funktionalität eines bot stark eingeschränkt. Bots in der Produktions Nutzung sollten als Teil einer APP zu Teams hinzugefügt werden. Weitere Informationen finden Sie unter [Erstellen eines bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create) und [Testen und Debuggen Ihres Microsoft Teams-bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)

<a name="create-custom-bots-for-microsoft-teams"></a>Erstellen von benutzerdefinierten Bots für Microsoft Teams
--------------------------------------

Mithilfe des Microsoft bot-Frameworks können Sie ganz einfach einen Bot erstellen, der sich in Ihre LOB-Anwendungen integriert. Lesen Sie den Leitfaden zum [Erstellen und Testen eines bot für Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) , um zu erfahren, wie Sie eigene Bots entwickeln und veröffentlichen können.

Wenn Sie einen Bot erstellen und in Bot Framework registrieren, können Sie wählen, ob er veröffentlicht werden soll. Wenn Sie den Bot nicht veröffentlichen, bleibt er privat. Sie können auch festlegen, dass sich die Benutzer vor der Verwendung des Bots anmelden müssen. Dadurch stellen Sie sicher, dass nur Mitarbeiter Ihrer Organisation auf den Bot zugreifen können, selbst wenn die Anwendungs-ID des Bots bekannt ist. Ein [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372)-Codebeispiel auf GitHub zeigt, wie Sie mithilfe von Bots Benutzer gegenüber Active Directory authentifizieren.

Bots können mit dem [Bot Framework-Emulator](https://go.microsoft.com/fwlink/?linkid=854373) getestet werden, bevor sie für Ihre Teams bereitgestellt werden.

<a name="upload-your-bot-for-personal-chat"></a>Laden Sie Ihren bot für persönlichen Chat hoch
---------------------------------------

1. Nachdem Sie Ihren bot erstellt haben, wechseln Sie zu den **Anwendungseinstellungen** für den von Ihnen entwickelten bot, und kopieren Sie dann unter **App-Einstellungen**den Wert der **MicrosoftAppId** -Einstellung. ![Screenshot der Seite "Anwendungseinstellungen" für einen bot](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  Wählen Sie in Teams im **Chat** Bereich das **Symbol Chat hinzufügen**aus. Fügen Sie in **an**die Microsoft- **App-ID**Ihres bot ein. ![Screenshot eines Chat Bereichs mit hervorgehobener Microsoft-App-ID](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3. Die APP-ID wird in Ihren **bot-Namen aufgelöst,** und Sie können dann mit diesem bot eine Chat Unterhaltung beginnen.

<a name="upload-your-bot-for-group-chats-or-channels"></a>Laden Sie Ihren bot für Gruppen-Chats oder-Kanäle hoch.
-----------------------------------

Wenn Sie Ihren bot für Ihre Kollegen freigeben möchten, gehen Sie wie folgt vor, um ihn Gruppen-Chats oder Kanälen in verschiedenen Teams hinzuzufügen:

1. Nachdem Sie [ein App-Paket für Ihren bot erstellt](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)haben, öffnen Sie Teams, und navigieren Sie zu dem Team, in dem Sie den bot hochladen werden.
2. Hinzufügen von **[App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, APP zu Teams.
3. Wählen Sie in App Studio die Registerkarte **Manifest-Editor** aus. ![Screenshot der Registerkarte Manifest-Editor.](media/Adding_Bot_To_Teams.png)
4. Um Ihren bot hinzuzufügen, wählen Sie in den Funktionen den bot aus und wählen Sie einen vorhandenen bot hinzufügen. Wählen Sie dann einen vorhandenen bot aus, oder geben Sie die ID eines vorhandenen bot ein.
![Zeigt die Auswahl des bereits erstellten bot an.](media/Select_Existing_Bot.png)
5. Navigieren Sie zum Speicherort des App-Pakets, wählen Sie es aus, und klicken Sie dann auf **Öffnen**.
6. Wählen Sie den Namen Ihres bot aus. (Vergessen Sie nicht, das Kontrollkästchen **Gruppen-Chat** oder **Team** unter dem Abschnitt Bereich zu aktivieren).
7. Wählen Sie **Testen und verteilen**aus.
8. Wählen Sie den Gruppen-Chat oder das Team aus, mit dem Sie Ihren bot verbinden möchten.

    Ihr bot steht in Ihrem Gruppen-Chat oder Team in Teams zur Verfügung.
