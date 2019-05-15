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
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier erhalten Sie Informationen zu PINs und zum Zurücksetzen von PINs in Microsoft Teams. '
ms.openlocfilehash: 56ea27ddf535f7ce23d5a25415b0a5921cfb2d6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33912303"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Zurücksetzen der Audiokonferenz-PIN in Microsoft Teams

Eine PIN ist ein aus Zahlen bestehender Code, der für jeden Microsoft Teams-Benutzer erstellt wird, der für Audiokonferenzen aktiviert ist. Besprechungsorganisatoren verwenden Audiokonferenz-PINs, um sich als Besprechungsorganisator auszuweisen und Besprechungen per Telefon zu starten. Wenn der Organisator zum Starten einer Besprechung die Microsoft Teams-App verwendet, ist keine PIN erforderlich. Wenn Benutzer ihre PIN vergessen und sie nicht in der E-Mail finden, die sie bei ihrer Aktivierung für Audiokonferenzen erhalten haben, kann die PIN von einem Administrator zurückgesetzt werden. Die Benutzer können ihre PIN auch selbst zurücksetzen.
  
Besprechungen können gestartet werden, wenn ein authentifizierter Benutzer über die Microsoft Teams-App teilnimmt oder wenn der Organisator per Telefon mit seiner PIN teilnimmt. Wenn die Besprechung zum Starten eine PIN erfordert, werden alle Benutzer, die sich per Telefon einwählen standardmäßig im Wartebereich platziert und hören Warteschleifenmusik, bis die Besprechung beginnt. Wenn der Organisator einer Besprechung keine PIN zum Starten der Besprechung per Telefon benötigt, werden Anrufer nicht nach einer PIN gefragt, wenn sie sich für die Besprechung einwählen.

## <a name="reset-a-users-pin"></a>Zurücksetzen der PIN eines Benutzers

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**

1. Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie auf **Bearbeiten**.

3. Klicken Sie unter **Audiokonferenzen**klicken Sie auf **PIN zurücksetzen**.

4. Klicken Sie auf **Zurücksetzen**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Ein Benutzer seine PIN zurücksetzen

1. Bitten Sie den Benutzer, wechseln Sie zur [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).
2. Klicken Sie auf **Zurücksetzen PIN**. 


## <a name="what-else-should-you-know-about-pins"></a>Was sollten Sie sonst über PINs wissen?

- Aus Sicherheitsgründen wird die PIN einem Administrator nur ein Mal gezeigt, wenn die PIN zurückgesetzt wird. Nachdem die PIN durch einen Administrator zurückgesetzt wird, werden die PIN-Nummer als aufgelistet ***.
    
- Automatisch Senden von e-Mails an Benutzer ist standardmäßig aktiviert, und Benutzer erhalten eine e-Mail mit ihrer PIN, wenn sie aktiviert sind, für Audiokonferenzen oder wenn die PIN zurückgesetzt wird. Aber wenn Sie automatisch deaktiviert haben Senden von e-Mails, eine PIN zurücksetzen-e-Mail wird nicht an einen Benutzer gesendet werden und Sie müssen die PIN-Informationen für den Benutzer manuell veranlassen.
    
- Beim Start einer Besprechung nehmen alle Benutzer im Wartebereich automatisch an dieser teil. Wenn beispielsweise 2 Teilnehmer versuchen, vor dem Start der Besprechung an dieser teilzunehmen, werden sie im Wartebereich platziert und hören Warteschleifenmusik. Sobald der Organisator der Besprechung mit seiner PIN per Telefon teilnimmt, beginnt die Besprechung und alle Teilnehmer im Wartebereich nehmen an der Besprechung teil.
    
- Die Standardeinstellung ist mit eine Besprechung gestartet werden, indem anonyme Anrufer nicht zu ermöglichen.
    
- Wenn Sie einen Benutzer für Audiokonferenzen aktivieren, werden standardmäßig sie-e-Mails gesendet, die Informationen zur Telefonkonferenz und ihre PIN enthalten. Der Benutzer muss ein Office 365-Postfach verfügen, da beim Zurücksetzen einer PIN ist eine neue PIN in e-Mails an ihre primäre SMTP-Adresse (Alias) an den Benutzer gesendet wird, die für den Benutzer festgelegt ist.
    
- Wenn Sie Audiokonferenzen eingerichtet haben, legen Sie die Ziffern, die für die PINs in Ihrer Organisation erforderlich sind. PINs können 4 bis 12 Ziffern enthalten, standardmäßig werden 5 Ziffern verwendet. Wenn Sie die PIN-Länge-Einstellung ändern, wird diese Einstellung gilt nur für neu generierte PINs und wird nicht angewendet, um die PIN-Einstellung für vorhandene Benutzer, die für Audiokonferenzen aktiviert sind. Finden Sie unter [Legen Sie die PIN für Audiokonferenzen Besprechungen](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).
    
- Die e-Mail standardmäßig wird auf die Office 365 primäre SMTP-Adresse des Benutzers festgelegt werden. Sie können eine e-Mail an eine nicht - Office 365-Adresse wie Hotmail oder MSN e-Mail-Adresse senden. Mithilfe von Windows PowerShell können Sie die Standard-e-Mail-Adresse außer Kraft setzen. Dies ist nützlich, wenn der Benutzer nicht über ein Exchange-Postfach in Office 365 verfügen.

    

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Verwandte Themen

[Zurücksetzen einer Konferenzkennung für einen Benutzer](reset-a-conference-id-for-a-user-in-teams.md)
