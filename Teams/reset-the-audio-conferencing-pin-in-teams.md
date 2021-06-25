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
description: Erfahren Sie, wie Sie die Audiokonferenz-PIN eines Benutzers in ihrem Microsoft Teams zurücksetzen, und erfahren Sie wichtige Informationen zu PINs.
ms.openlocfilehash: 6470085fed25a83c1a8dc46ab45e8c6ea57b5603
ms.sourcegitcommit: a07040d1527692b4dbde7bd2c21994377ad0a92e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53114024"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Zurücksetzen der Audiokonferenz-PIN in Microsoft Teams

Eine PIN ist ein aus Zahlen besteht Code, der für jeden benutzer Microsoft Teams der für Audiokonferenzen aktiviert ist, erstellt wird. Audiokonferenzen PINs werden von Besprechungsorganisatoren verwendet, um zu identifizieren, dass sie der Besprechungsorganisator sind, und es ihnen zu ermöglichen, eine Besprechung per Telefon zu starten. Wenn er die Microsoft Teams-App zum Starten der Besprechung verwendet, ist keine PIN erforderlich. Wenn Benutzer ihre PIN vergessen und diese in der E-Mail, die ihnen bei der Aktivierung für Audiokonferenzen gesendet wurde, nicht finden können, kann ein Administrator ihre PIN oder ihre eigene PIN zurücksetzen.
  
Besprechungen können gestartet werden, wenn ein authentifizierter Benutzer mit der Microsoft Teams-App teilnimmt oder der Organisator per Telefon mit seiner PIN teilnimmt. Wenn für eine Besprechung zum Starten eine PIN erforderlich ist, werden Benutzer, die per Telefon teilnehmen, in den Wartebereich platziert und hören warteMusik, bis der Organisator sie zugibt. Wenn der Organisator einer Besprechung keine PIN zum Starten der Besprechung per Telefon benötigt, werden Anrufer nicht nach einer PIN gefragt, wenn sie sich für die Besprechung einwählen.

## <a name="reset-a-users-pin"></a>Zurücksetzen der PIN eines Benutzers

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie im linken Navigationsbereich auf **Benutzer**, und wählen Sie den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie **auf Bearbeiten**.

3. Klicken **Sie unter Audiokonferenzen** auf **PIN zurücksetzen**.

4. Klicken Sie **auf Zurücksetzen**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a>Benutzer die eigene PIN zurücksetzen

1. Lassen Sie den Benutzer zu [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) wechseln.
2. Klicken Sie **auf PIN zurücksetzen**. 

> [!NOTE]
> Für GGCH gehen Sie zu: https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing .

## <a name="what-else-should-you-know-about-pins"></a>Was sollten Sie sonst über PINs wissen?

- Aus Sicherheitsgründen wird die PIN einem Administrator nur einmal angezeigt, wenn die PIN zurückgesetzt wird. Nachdem die PIN von einem Administrator zurückgesetzt wurde, wird die PIN als ***********angezeigt.
    
- Das automatische Senden von E-Mails an Benutzer ist standardmäßig aktiviert, und Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert oder die PIN zurückgesetzt wird. Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird keine E-Mail zum Zurücksetzen der PIN an einen Benutzer gesendet, und Sie müssen die PIN-Informationen manuell an den Benutzer senden.
    
- Wenn eine Besprechung beginnt, muss der Organisator alle PSTN-Benutzer im Wartebereich einräumen, um an der Besprechung teilnehmen zu können. Wenn beispielsweise zwei PSTN-Teilnehmer versuchen, vor dem Beginn einer Besprechung an einer Besprechung teilzugeben, werden sie in den Wartebereich setzen und hören Warteschleifenmusik, und wenn der Organisator der Besprechung per Telefon mit seiner PIN beitritt, wird die Besprechung gestartet, und der Organisator kann den In-Meeting-Befehl (drücken Sie *21) verwenden, um alle PSTN-Benutzer im Wartebereich einzuräumen.
    
- Die Standardeinstellung ist, dass das Starten einer Besprechung durch anonyme Anrufer nicht zulässig ist.
    
- Wenn Sie einen Benutzer für Audiokonferenzen aktivieren, wird ihm standardmäßig eine E-Mail gesendet, die Konferenzinformationen und die eigene PIN enthält. Der Benutzer muss über ein Microsoft 365- oder Office 365-Postfach verfügen, da beim Zurücksetzen einer PIN eine neue PIN per E-Mail an die für den Benutzer festgelegte primäre SMTP-Adresse (Alias) gesendet wird.
    
- Wenn Sie Audiokonferenzen einrichten, legen Sie die Ziffern fest, die für die PINs in Ihrer Organisation erforderlich sind. PINs können 4 bis 12 Ziffern enthalten, standardmäßig werden 5 Ziffern verwendet. Wenn Sie die PIN-Längeneinstellung ändern, wird die Einstellung nur auf neu generierte PINs angewendet und nicht auf PIN-Einstellungen für vorhandene Benutzer, die für Audiokonferenzen aktiviert sind. Weitere [Informationen finden Sie unter Festlegen der Länge der PIN für Audiokonferenzbesprechungen.](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)
    
- Die E-Mail wird standardmäßig auf die adresse Microsoft 365 oder Office 365 SMTP-Adresse des Benutzers festgelegt. Sie können eine E-Mail an eine nicht Microsoft 365 oder nicht Office 365, z. B. Hotmail MSN-E-Mail-Adresse, senden. Sie können die standardmäßige E-Mail-Adresse außer Kraft setzen, indem Sie Windows PowerShell. Dies ist nützlich, wenn die Benutzer nicht über ein Postfach Exchange postfach in Microsoft 365 oder Office 365.

    

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe eines einzigen Administrationspunkts verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Verwandte Themen

[Zurücksetzen einer Konferenzkennung für einen Benutzer](reset-a-conference-id-for-a-user-in-teams.md)
