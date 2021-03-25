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
description: Erfahren Sie, wie Sie die PIN für Audiokonferenzen eines Benutzers in Microsoft Teams zurücksetzen und wichtige Fakten zu PINs erfahren.
ms.openlocfilehash: 7ea380fbeb722337eaec598823b12dbe18f49918
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117633"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Zurücksetzen der Audiokonferenz-PIN in Microsoft Teams

Eine PIN ist ein Code, der aus Zahlen besteht, der für jeden Microsoft Teams-Benutzer erstellt wird, der für Audiokonferenzen aktiviert ist. Pins für Audiokonferenzen werden von Besprechungsorganisatoren verwendet, um zu erkennen, dass sie der Besprechungsorganisator sind und es ihnen ermöglichen, eine Besprechung über das Telefon zu starten. Wenn sie die Besprechung mithilfe der Microsoft Teams-App starten, ist keine PIN erforderlich. Wenn Benutzer ihre PIN vergessen und sie in der E-Mail, die ihnen gesendet wurde, als sie für Audiokonferenzen aktiviert wurden, nicht finden können, kann ein Administrator seine PIN zurücksetzen oder seine eigene PIN zurücksetzen.
  
Besprechungen können gestartet werden, wenn ein authentifizierter Benutzer über die Microsoft Teams-App beitritt oder wenn der Organisator über das Telefon mit seiner PIN beitritt. Wenn die Besprechung zum Starten eine PIN erfordert, werden alle Benutzer, die sich per Telefon einwählen standardmäßig im Wartebereich platziert und hören Warteschleifenmusik, bis die Besprechung beginnt. Wenn der Organisator einer Besprechung keine PIN zum Starten der Besprechung per Telefon benötigt, werden Anrufer nicht nach einer PIN gefragt, wenn sie sich für die Besprechung einwählen.

## <a name="reset-a-users-pin"></a>Zurücksetzen der PIN eines Benutzers

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie im linken Navigationsbereich auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie **auf Bearbeiten**.

3. Klicken **Sie unter Audiokonferenzen** auf **PIN zurücksetzen.**

4. Klicken Sie **auf Zurücksetzen.**
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a>Zurücksetzen einer eigenen PIN durch einen Benutzer

1. Lassen Sie den Benutzer zu [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) wechseln.
2. Klicken Sie **auf PIN zurücksetzen.** 

> [!NOTE]
> Für GCCH wechseln Sie zu: https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing .

## <a name="what-else-should-you-know-about-pins"></a>Was sollten Sie sonst über PINs wissen?

- Aus Sicherheitsgründen wird die PIN nur einmal einem Administrator angezeigt, wenn die PIN zurückgesetzt wird. Nachdem die PIN von einem Administrator zurückgesetzt wurde, wird die PIN als *********** aufgelistet.
    
- Das automatische Senden von E-Mails an Benutzer ist standardmäßig aktiviert, und Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert sind oder wenn die PIN zurückgesetzt wird. Wenn Sie jedoch das automatische Senden von E-Mails deaktiviert haben, wird keine E-Mail zum Zurücksetzen der PIN an einen Benutzer gesendet, und Sie müssen die PIN-Informationen manuell an den Benutzer senden.
    
- Wenn eine Besprechung beginnt, nehmen alle Benutzer im Wartebereich automatisch an der Besprechung teil. Wenn z. B. zwei Teilnehmer versuchen, an einer Besprechung zu teilnehmen, bevor sie begonnen wurde, werden sie in den Wartebereich ein- und hören Musik im Haltebereich, und wenn der Besprechungsorganisator über seine PIN per Telefon beitritt, beginnt die Besprechung, und die Teilnehmer im Wartebereich nehmen an der Besprechung teil.
    
- Die Standardeinstellung besteht im Nichtanrufen einer Besprechung durch anonyme Anrufer.
    
- Wenn Sie einen Benutzer für Audiokonferenzen aktivieren, werden standardmäßig E-Mails gesendet, die Konferenzinformationen und deren PIN enthalten. Der Benutzer muss über ein Microsoft 365- oder Office 365-Postfach verfügen, da beim Zurücksetzen einer PIN eine neue PIN per E-Mail an die primäre SMTP-Adresse (Alias) gesendet wird, die für den Benutzer festgelegt ist.
    
- Wenn Sie Audiokonferenzen einrichten, legen Sie die Ziffern fest, die für die PINs in Ihrer Organisation erforderlich sind. PINs können 4 bis 12 Ziffern enthalten, standardmäßig werden 5 Ziffern verwendet. Wenn Sie die Einstellung für die PIN-Länge ändern, wird die Einstellung nur auf neu generierte PINs angewendet und nicht auf die PIN-Einstellung für vorhandene Benutzer angewendet, die für Audiokonferenzen aktiviert sind. Weitere Informationen finden Sie unter Festlegen [der Länge der PIN für Audiokonferenzbesprechungen.](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)
    
- Die E-Mail wird standardmäßig auf die primäre MICROSOFT 365- oder Office 365-SMTP-Adresse des Benutzers festgelegt. Sie können eine E-Mail an eine Nicht-Microsoft 365- oder nicht Office 365-Adresse senden, z. B. eine Hotmail oder MSN-E-Mail-Adresse. Sie können die Standard-E-Mail-Adresse überschreiben, indem Sie Windows PowerShell. Dies ist nützlich, wenn die Benutzer kein Exchange-Postfach in Microsoft 365 oder Office 365 haben.

    

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe eines einzelnen Verwaltungspunkts verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Verwandte Themen

[Zurücksetzen einer Konferenzkennung für einen Benutzer](reset-a-conference-id-for-a-user-in-teams.md)