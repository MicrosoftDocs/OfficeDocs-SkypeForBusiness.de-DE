---
title: Zurücksetzen der Audiokonferenz-PIN in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie die Audiokonferenz-PIN eines Benutzers in Microsoft Teams zurücksetzen, und erfahren Sie wichtige Informationen zu PINs.
ms.openlocfilehash: 3f1055551edb45ac422052476196f01ee4d2765d
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237465"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Zurücksetzen der Audiokonferenz-PIN in Microsoft Teams

Eine PIN ist ein aus Zahlen bestehender Code, der für jeden Microsoft Teams-Benutzer erstellt wird, der für Audiokonferenzen aktiviert ist. Besprechungsorganisatoren verwenden Audiokonferenz-PINs, um sich als Besprechungsorganisator auszuweisen und Besprechungen per Telefon zu starten. Wenn der Organisator zum Starten einer Besprechung die Microsoft Teams-App verwendet, ist keine PIN erforderlich. Wenn Benutzer ihre PIN vergessen und sie nicht in der E-Mail finden, die sie bei ihrer Aktivierung für Audiokonferenzen erhalten haben, kann die PIN von einem Administrator zurückgesetzt werden. Die Benutzer können ihre PIN auch selbst zurücksetzen.
  
Besprechungen können gestartet werden, wenn ein authentifizierter Benutzer über die Microsoft Teams-App teilnimmt oder der Organisator per Telefon mit seiner PIN teilnimmt. Wenn die Besprechung zum Starten eine PIN erfordert, werden alle Benutzer, die sich per Telefon einwählen standardmäßig im Wartebereich platziert und hören Warteschleifenmusik, bis die Besprechung beginnt. Wenn der Organisator einer Besprechung keine PIN zum Starten der Besprechung per Telefon benötigt, werden Anrufer nicht nach einer PIN gefragt, wenn sie sich für die Besprechung einwählen.

## <a name="reset-a-users-pin"></a>Zurücksetzen der PIN eines Benutzers

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie im linken Navigationsbereich auf **"Benutzer",** und wählen Sie den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie **auf "Bearbeiten".**

3. Klicken **Sie unter "Audiokonferenzen" auf** **"PIN zurücksetzen".**

4. Klicken Sie **auf "Zurücksetzen".**
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a>Benutzer müssen ihre eigene PIN zurücksetzen

1. Lassen Sie den Benutzer zu [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) .
2. Klicken Sie **auf "PIN zurücksetzen".** 


## <a name="what-else-should-you-know-about-pins"></a>Was sollten Sie sonst über PINs wissen?

- Aus Sicherheitsgründen wird die PIN einem Administrator nur einmal angezeigt, wenn die PIN zurückgesetzt wird. Nach dem Zurücksetzen der PIN durch einen Administrator wird die PIN als "*******" aufgeführt.
    
- Das automatische Senden von E-Mails an Benutzer ist standardmäßig aktiviert, und Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert sind oder die PIN zurückgesetzt wird. Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird keine E-Mail zum Zurücksetzen einer PIN an einen Benutzer gesendet, und Sie müssen die PIN-Informationen manuell an den Benutzer senden.
    
- Wenn eine Besprechung beginnt, nehmen alle Benutzer im Wartebereich automatisch an der Besprechung teil. Wenn beispielsweise zwei Teilnehmer versuchen, an einer Besprechung zu teilnehmen, bevor sie gestartet wurde, werden sie in den Wartebereich gelaufen und hören Warteschleifenmusik. Wenn der Besprechungsorganisator per Telefon mit seiner PIN teilniert, beginnt die Besprechung, und die Teilnehmer im Wartebereich nehmen an der Besprechung teil.
    
- Die Standardeinstellung ist, dass das Starten einer Besprechung durch anonyme Anrufer nicht zulässig ist.
    
- Wenn Sie einen Benutzer für Audiokonferenzen aktivieren, wird ihm standardmäßig eine E-Mail gesendet, die Konferenzinformationen und seine PIN enthält. Der Benutzer muss über ein Microsoft 365- oder Office 365-Postfach verfügen, da beim Zurücksetzen einer PIN eine neue PIN per E-Mail an die primäre SMTP-Adresse (Alias) gesendet wird, die für den Benutzer festgelegt ist.
    
- Wenn Sie Audiokonferenzen einrichten, legen Sie die Ziffern fest, die für die PINs in Ihrer Organisation erforderlich sind. PINs können 4 bis 12 Ziffern enthalten, standardmäßig werden 5 Ziffern verwendet. Wenn Sie die Längeneinstellung der PIN ändern, wird die Einstellung nur auf neu generierte PINs angewendet und nicht auf die PIN-Einstellung für vorhandene Benutzer, die für Audiokonferenzen aktiviert sind. Informationen [finden Sie unter Festlegen der Länge der PIN für Audiokonferenzbesprechungen.](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)
    
- Die E-Mail wird standardmäßig auf die primäre E-Mail-Adresse des Benutzers für Microsoft 365 oder Office 365 festgelegt. Sie können eine E-Mail an eine E-Mail-Adresse senden, die nicht zu Microsoft 365 oder nicht zu Office 365 da ist, z. B. an eine Hotmail oder MSN-E-Mail-Adresse. Sie können die Standard-E-Mail-Adresse mithilfe von Windows PowerShell. Dies ist nützlich, wenn die Benutzer nicht über ein Exchange-Postfach in Microsoft 365 oder Office 365 verfügen.

    

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Die besten Methoden zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Verwandte Themen

[Zurücksetzen einer Konferenzkennung für einen Benutzer](reset-a-conference-id-for-a-user-in-teams.md)
