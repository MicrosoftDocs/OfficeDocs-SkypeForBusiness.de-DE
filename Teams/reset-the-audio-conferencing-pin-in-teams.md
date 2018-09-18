---
title: Zurücksetzen der Audiokonferenz-PIN in Microsoft Teams
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier erhalten Sie Informationen zu PINs und zum Zurücksetzen von PINs in Microsoft Teams. '
ms.openlocfilehash: 9c63df504150dce7ba1d46329fc86a27c75ced8d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892954"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Zurücksetzen der Audiokonferenz-PIN in Microsoft Teams

Eine PIN ist ein aus Zahlen bestehender Code, der für jeden Microsoft Teams-Benutzer erstellt wird, der für Audiokonferenzen aktiviert ist. Besprechungsorganisatoren verwenden Audiokonferenz-PINs, um sich als Besprechungsorganisator auszuweisen und Besprechungen per Telefon zu starten. Wenn der Organisator zum Starten einer Besprechung die Microsoft Teams-App verwendet, ist keine PIN erforderlich. Wenn Benutzer ihre PIN vergessen und sie nicht in der E-Mail finden, die sie bei ihrer Aktivierung für Audiokonferenzen erhalten haben, kann die PIN von einem Administrator zurückgesetzt werden. Die Benutzer können ihre PIN auch selbst zurücksetzen.
  
Besprechungen können gestartet werden, wenn ein authentifizierter Benutzer über die Microsoft Teams-App teilnimmt oder wenn der Organisator per Telefon mit seiner PIN teilnimmt. Wenn die Besprechung zum Starten eine PIN erfordert, werden alle Benutzer, die sich per Telefon einwählen standardmäßig im Wartebereich platziert und hören Warteschleifenmusik, bis die Besprechung beginnt. Wenn der Organisator einer Besprechung keine PIN zum Starten der Besprechung per Telefon benötigt, werden Anrufer nicht nach einer PIN gefragt, wenn sie sich für die Besprechung einwählen.

## <a name="reset-a-users-pin"></a>Zurücksetzen der PIN eines Benutzers

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.

2. Klicken Sie oben auf der Seite auf **Bearbeiten**.

3. Klicken Sie unter **Audiokonferenz** auf **PIN zurücksetzen**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Einen Benutzer die eigene PIN zurücksetzen lassen

1. Bitten Sie den Benutzer, zu [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) zu navigieren.
2. Dort muss der Benutzer auf **PIN zurücksetzen** klicken. 


## <a name="what-else-should-you-know-about-pins"></a>Was sollten Sie sonst über PINs wissen?

- Aus Sicherheitsgründen wird die PIN einem Administrator nur ein Mal angezeigt, wenn die PIN zurückgesetzt wird. Nach dem Zurücksetzen der PIN durch einen Administrator wird die PIN als *********** dargestellt.
    
- Das automatische Senden von E-Mails an Benutzer ist standardmäßig aktiviert, und Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert werden oder ihre PIN zurückgesetzt wird. Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird allerdings keine E-Mail zum Zurücksetzen der PIN gesendet. In diesem Fall müssen Sie die PIN manuell an die Benutzer senden.
    
- Beim Start einer Besprechung nehmen alle Benutzer im Wartebereich automatisch an dieser teil. Wenn beispielsweise 2 Teilnehmer versuchen, vor dem Start der Besprechung an dieser teilzunehmen, werden sie im Wartebereich platziert und hören Warteschleifenmusik. Sobald der Organisator der Besprechung mit seiner PIN per Telefon teilnimmt, beginnt die Besprechung und alle Teilnehmer im Wartebereich nehmen an der Besprechung teil.
    
- Die Standardeinstellung sieht vor, dass Besprechungen nicht von anonymen Anrufern gestartet werden können.
    
- Wenn Sie Benutzer für Audiokonferenzen aktivieren, erhalten diese standardmäßig eine E-Mail mit Konferenzinformationen und ihrer PIN. Die Benutzer müssen über ein Office 365-Postfach verfügen, da beim Zurücksetzen ihrer PIN eine neue PIN per E-Mail an die primäre für sie festgelegte SMTP-Adresse (Alias) gesendet wird.
    
- Beim Einrichten von Audiokonferenzen legen Sie die Ziffern fest, die für die PINs in Ihrer Organisation erforderlich sind. PINs können vier bis zwölf Ziffern enthalten. Standardmäßig werden fünf Ziffern verwendet. Wenn Sie die Einstellung für die PIN-Länge ändern, wird die Änderung nur auf neu generierte PINs angewendet und nicht auf PIN-Einstellungen vorhandener Benutzer, die bereits für Audiokonferenzen aktiviert sind. Weitere Informationen finden Sie unter [Festlegen der Länge der PIN für Audiokonferenzbesprechungen](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).
    
- Die E-Mail wird standardmäßig an die in Office 365 festgelegte primäre SMTP-Adresse des Benutzers gesendet. Sie können auch eine E-Mail an eine nicht in Office 365 festgelegte Adresse senden, zum Beispiel an eine Hotmail- oder MSN-E-Mail-Adresse. Sie können die standardmäßige E-Mail-Adresse mithilfe von Windows PowerShell außer Kraft setzen. Dies ist hilfreich, wenn die Benutzer kein Exchange-Postfach in Office 365 haben.

    

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Verwandte Themen

[Zurücksetzen einer Konferenzkennung für einen Benutzer](reset-a-conference-id-for-a-user-in-teams.md)
