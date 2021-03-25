---
title: Starten einer Audiokonferenz über das Telefon ohne PIN in Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
- seo-marvel-mar2020
description: 'Erfahren Sie, wie Sie anonyme Anrufer über das Teams Admin Center an einer Besprechung aktivieren oder deaktivieren können. '
ms.openlocfilehash: 520bf720a01a686a103748cdbbf26cb8426e94f2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116963"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Starten einer Audiokonferenz per Telefon ohne PIN in Microsoft Teams

Es kann frustrierend sein, wenn Benutzer, die sich zu einer Besprechung einwählen, im Wartebereich der Besprechung Musik hören, weil der Organisator der Microsoft Teams-Besprechung die Besprechung noch nicht gestartet hat. 
  
Wenn sich ein Besprechungsorganisator bei der Besprechung ein aufruft, ist standardmäßig eine PIN erforderlich, um eine Besprechung zu starten. Sie können sie so einrichten, dass jeder sich zu einer Besprechung einwählen kann und nicht aufgefordert wird, eine PIN zum Starten der Besprechung zu erhalten. Sie können das Admin Center verwenden, um diese Einstellung für einen einzelnen Benutzer zu aktivieren oder zu deaktivieren.
  
Eine PIN ist für den Besprechungsorganisator nicht erforderlich, wenn jemand die Besprechung über die Microsoft Teams-App gestartet hat. Eine PIN ist nur erforderlich, wenn der Organisator einer Besprechung per Telefon an der Besprechung teilnimmt. Die PIN für Besprechungen wird an den Audiobenutzer gesendet, wenn ihm die Lizenz für **Audiokonferenzen** zugewiesen wurde und für Audiokonferenzen aktiviert ist. Weitere Informationen finden Sie unter Senden einer E-Mail an einen Benutzer mit seinen [Audiokonferenzinformationen](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) und E-Mails, die automatisch an Benutzer gesendet werden, wenn sich die Einstellungen für [Audiokonferenzen ändern.](emails-sent-to-users-when-their-settings-change-in-teams.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Aktivieren oder Deaktivieren anonymer Anrufer für die Teilnahme an einer Besprechung

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie im linken Navigationsbereich auf **Benutzer**. 

2. Wählen Sie einen Benutzer in der  Liste aus, und klicken Sie dann oben auf der Seite auf Bearbeiten. 

3. Klicken Sie **neben Audiokonferenzen** auf **Bearbeiten.**

4. Im Bereich **Audiokonferenzen** können Einwahlanrufer als erste Person in einer Besprechung aktiviert oder **deaktiviert werden.**
    
4. Klicken Sie auf **Anwenden**. 

**Verwenden von Windows PowerShell**
  
Weitere Informationen finden Sie in der [Microsoft Teams PowerShell-Referenz.](/powershell/module/teams/?view=teams-ps)

## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

- Wenn Sie die PIN zurücksetzen möchten, lesen [Sie Zurücksetzen der PIN für Audiokonferenzen.](reset-the-audio-conferencing-pin-in-teams.md)
    
- Wenn der anonyme Zugriff deaktiviert ist oder keine PIN zum Starten einer Besprechung erforderlich ist:
    
  - Wenn die Besprechung noch nicht begonnen hat (es ist noch niemand in der Besprechung): Ein Anrufer wird aufgefordert, wenn er der Organisator ist. Wenn er "Ja" sagt, wird er zur Eingabe seiner PIN aufgefordert, und nach eingabe der PIN wird die Besprechung gestartet, und der Benutzer wird an der Besprechung teilnehmen.
    
  - Wenn die Besprechung bereits begonnen hat (eine andere Person ist bereits in der Besprechung): Ein Anrufer wird nicht aufgefordert, wenn er der Organisator ist, und er wird nie zur PIN aufgefordert. die Besprechung ist bereits gestartet, und der Anrufer wird ihr beitreten.
    
- Wenn anonymer Zugriff aktiviert ist oder keine PIN zum Starten einer Besprechung erforderlich ist:
    
  - Wenn die Besprechung noch nicht begonnen hat (es gibt noch niemand in der Besprechung): Ein Anrufer wird nicht aufgefordert, wenn er der Organisator ist, und er wird nie zur PIN aufgefordert. Da die Einstellung des Organisators deaktiviert ist, wird die Besprechung gestartet, und die anonymen Anrufer nehmen an der Besprechung teil.
    
  - Wenn die Besprechung bereits begonnen hat (eine andere Person befindet sich bereits in der Besprechung): Ein Anrufer wird nicht aufgefordert, wenn er der Organisator ist, und er wird nie zur PIN aufgefordert. Die Besprechung wurde bereits gestartet, und der Anrufer wird an der Besprechung teilnehmen.
    
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe eines einzelnen Verwaltungspunkts verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)