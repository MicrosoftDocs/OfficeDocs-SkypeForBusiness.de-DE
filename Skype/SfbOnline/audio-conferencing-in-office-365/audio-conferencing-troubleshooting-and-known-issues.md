---
title: Problembehandlung und bekannte Probleme bei Audiokonferenzen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Hier finden Sie eine Liste der bekannten Probleme, die bei der Verwendung von Microsoft als Anbieter von Einwahlkonferenzen auftreten, sowie den Status und einige Problemumgehungen. '
ms.openlocfilehash: 71d363ff98fc4590fb6d96cc3e8a8cb77b1fa24c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237191"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Problembehandlung und bekannte Probleme bei Audiokonferenzen

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 **Dieser Artikel ist für Skype for Business, die Microsoft als Audiokonferenzanbieter verwenden. Sie gelten nicht für Kunden, die einen Drittanbieter für Audiokonferenzen (Audio Conferencing Provider, ACP) verwenden.**
  
## <a name="troubleshooting-and-known-issues"></a>Problembehandlung und bekannte Probleme

Bei Audiokonferenzen, bei denen Microsoft als Audiokonferenzanbieter verwendet wird, gibt es aktuelle Probleme, die nachverfolgt und aktiv untersucht werden und möglicherweise gelöst werden, wenn das Feature in zukünftigen Versionen von Microsoft 365 aktualisiert wird.
  
Verwenden Sie diese Informationen vorerst als Referenz, wenn Sie potenzielle Probleme beim Einrichten und Arbeiten von Audiokonferenzen für die Personen in Skype for Business Organisation beheben möchten.

|**Problem**|**Verhalten/Symptome**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Benachrichtigungen bei Zu- oder Abgang sind zu Beginn einer Besprechung aktiviert, werden aber kurz darauf deaktiviert.  <br/> |Die Benachrichtigungen bei Zu- oder Abgang sind für Besprechungen, an denen Teilnehmer sowohl über Skype for Business-Apps als auch per Einwahl teilnehmen, standardmäßig deaktiviert. Sie können die Ankündigungen in den **Skype-Besprechungsoptionen** in der Skype for Business-App aktivieren. Bei einer Besprechung, an der alle Teilnehmer durch Einwahl teilnehmen, sind die Benachrichtigungen bei Zu- oder Abgang standardmäßig aktiviert, da den Teilnehmern keine Teilnehmerliste zur Verfügung steht. Wenn eine Besprechung ausschließlich mit Teilnehmern begonnen hat, die durch Einwahl teilnehmen, werden die Benachrichtigungen bei Zu- oder Abgang aktiviert. Wenn jedoch ein Teilnehmer über eine Skype for Business-App teilnimmt, werden die Benachrichtigungen deaktiviert. Deaktivierte Benachrichtigungen können mithilfe der **Skype-Besprechungsoptionen** in der Skype for Business-App wieder aktiviert werden. <br/> |Keine Problemumgehung  <br/> |30.8.2017  <br/> |
|Wenn ein Benutzer durch Zuweisen einer E5-Lizenz erstmals bereitgestellt wird und das Postfach nicht aktiviert ist, wird die Begrüßungs-E-Mail für Audiokonferenzen möglicherweise nicht zugestellt.  <br/> |In diesem Fall können Sie die Informationen zur Audiokonferenz jederzeit mit der Option **Audio conferencing** (Audiokonferenz) im Skype for Business Admin Center oder mit PowerShell erneut an den Benutzer senden. Siehe [Aktivieren oder Deaktivieren des Sendens von E-Mails, wenn sich die Audiokonferenzeinstellungen ändern.](enable-or-disable-sending-emails-when-their-settings-change.md)  <br/> **Hinweis:** Um die Audiokonferenz-PIN erneut an den Benutzer zu senden, muss die PIN zurückgesetzt werden. Dies kann auch über **Audio conferencing (Audiokonferenz)** im Skype for Business Admin Center oder mithilfe von PowerShell geschehen.          |Keine Problemumgehung  <br/> |30.8.2017  <br/> |
|Es kann bis zu 24 Stunden dauern, bis Audiokonferenzanrufe in den Nutzungsberichten angezeigt werden.  <br/> |Für diesen Bereich sind in zukünftigen Dienstupdates Verbesserungen geplant.  <br/> |Keine Problemumgehung  <br/> |30.8.2017  <br/> |
|Wenn sich ein Anrufer in eine Konferenzbrücke einwählt, nachdem die Besprechung von einem Skype for Business-Benutzer gesperrt wurde, wird in derSkype for Business-App keine Benachrichtigung dazu angezeigt, dass der Benutzer im Wartebereich wartet.  <br/> |Dies ist zurzeit entwurfsbedingt, wir werden jedoch Ihr Feedback hinsichtlich der Unterstützung dieser Funktion in zukünftigen Dienstupdates berücksichtigen.  <br/> |Keine Problemumgehung  <br/> |30.8.2017  <br/> |
|Einem Skype for Business Server (vor dem 1. März 2019) zugewiesenen Benutzer (vor dem 1. März 2019) werden die Einwahlkoordinaten in ihren Besprechungseinrufen möglicherweise nicht angezeigt.  <br/> |Die bereitstellung Skype for Business Server für Teams Audiokonferenzen wurde bis zu diesem Datum nicht unterstützt. Sie wird jetzt unterstützt und ist Eine Komponente von ["Meetings First"](/microsoftteams/meetings-first). Der Benutzer muss über eine Lizenz Teams verfügen.  <br/> |Die Bereitstellungspipeline muss erneut aktiviert werden. Entfernen Sie die Lizenz für Audiokonferenzen des Benutzers, warten Sie einige Stunden, undzuweisen Sie die Lizenz erneut.  <br/> |01.03.2019  <br/> |
   
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
