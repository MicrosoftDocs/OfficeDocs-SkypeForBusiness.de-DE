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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Rufen Sie eine Liste bekannter Probleme ab, wenn Sie Microsoft als Einwahlkonferenz Anbieter, Status und einige Problemumgehungen verwenden. '
ms.openlocfilehash: bfb76c23d3b1235bf67435e0af09ddef2a8852f3
ms.sourcegitcommit: bb8577aca8c7e0673b37634a24bf793c86c0537b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2019
ms.locfileid: "36675237"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Problembehandlung und bekannte Probleme bei Audiokonferenzen

 **Dieser Artikel befasst sich mit Skype for Business-Benutzern, die Microsoft als Anbieter von Audiokonferenzen verwenden. Dies gilt nicht für Kunden, die einen Drittanbieter für Audiokonferenzen (ACP) verwenden.**
  
## <a name="troubleshooting-and-known-issues"></a>Problembehandlung und bekannte Probleme

Bei Audiokonferenzen mit Microsoft als Audiokonferenzanbieter sind aktuelle Probleme bekannt, die nachverfolgt, aktiv untersucht und potentiell gelöst werden, wenn die Funktion in zukünftigen Versionen von Office 365 aktualisiert wird.
  
Verwenden Sie diese Option im Moment als Referenz, wenn Sie mögliche Probleme beim Einrichten und Arbeiten von Audiokonferenzen für Personen, die Skype for Business in Ihrer Organisation verwenden, beheben möchten.

|**Problem**|**Verhalten/Symptome**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Benachrichtigungen bei Zu- oder Abgang sind zu Beginn einer Besprechung aktiviert, werden aber kurz darauf deaktiviert.  <br/> |Die Benachrichtigungen bei Zu- oder Abgang sind für Besprechungen, an denen Teilnehmer sowohl über Skype for Business-Apps als auch per Einwahl teilnehmen, standardmäßig deaktiviert. Sie können die Ankündigungen in den **Skype-Besprechungsoptionen** in der Skype for Business-App aktivieren. Bei einer Besprechung, an der alle Teilnehmer durch Einwahl teilnehmen, sind die Benachrichtigungen bei Zu- oder Abgang standardmäßig aktiviert, da den Teilnehmern keine Teilnehmerliste zur Verfügung steht. Wenn eine Besprechung ausschließlich mit Teilnehmern begonnen hat, die durch Einwahl teilnehmen, werden die Benachrichtigungen bei Zu- oder Abgang aktiviert. Wenn jedoch ein Teilnehmer über eine Skype for Business-App teilnimmt, werden die Benachrichtigungen deaktiviert. Deaktivierte Benachrichtigungen können mithilfe der **Skype-Besprechungsoptionen** in der Skype for Business-App wieder aktiviert werden. <br/> |Keine Problemumgehung  <br/> |30.8.2017  <br/> |
|Wenn ein Benutzer durch Zuweisen einer E5-Lizenz erstmals bereitgestellt wird und das Postfach nicht aktiviert ist, wird die Begrüßungs-E-Mail für Audiokonferenzen möglicherweise nicht zugestellt.  <br/> |In diesem Fall können Sie die Informationen zur Audiokonferenz jederzeit mit der Option **Audio conferencing** (Audiokonferenz) im Skype for Business Admin Center oder mit PowerShell erneut an den Benutzer senden. Weitere Informationen finden Sie unter [Aktivieren oder deaktivieren](enable-or-disable-sending-emails-when-their-settings-change.md)des Sendens von e-Mails, wenn audiokonferenzeinstellungen geändert werden.  <br/> **Hinweis:** Um die PIN für die Audiokonferenz an den Benutzer erneut zu senden, muss die PIN zurückgesetzt werden. Dies kann auch mithilfe von Audiokonferenzen **** im Skype for Business Admin Center oder mithilfe von PowerShell erfolgen.          |Keine Problemumgehung  <br/> |30.8.2017  <br/> |
|Es kann bis zu 24 Stunden dauern, bis Audiokonferenzanrufe in den Nutzungsberichten angezeigt werden.  <br/> |Für diesen Bereich sind in zukünftigen Dienstupdates Verbesserungen geplant.  <br/> |Keine Problemumgehung  <br/> |30.8.2017  <br/> |
|Wenn sich ein Anrufer in eine Konferenzbrücke einwählt, nachdem die Besprechung von einem Skype for Business-Benutzer gesperrt wurde, wird in derSkype for Business-App keine Benachrichtigung dazu angezeigt, dass der Benutzer im Wartebereich wartet.  <br/> |Dies ist zurzeit entwurfsbedingt, wir werden jedoch Ihr Feedback hinsichtlich der Unterstützung dieser Funktion in zukünftigen Dienstupdates berücksichtigen.  <br/> |Keine Problemumgehung  <br/> |30.8.2017  <br/> |
|Ein Skype for Business Server (on-Prem)-Benutzer, dem die Audiokonferenz-Lizenz vor dem 1. März 2019 zugewiesen wurde, wird möglicherweise nicht in seinen Besprechungseinladungen die Einwahl Koordinaten angezeigt.  <br/> |Die Bereitstellung von Skype for Business Server-Benutzern für Teams-Audiokonferenzen wurde bis zu diesem Datum nicht unterstützt. Sie wird jetzt unterstützt und ist eine Komponente [](https://docs.microsoft.com/microsoftteams/meetings-first)von Besprechungen. Der Benutzer muss über eine Teams-Lizenz verfügen.  <br/> |Die Bereitstellungs Pipeline muss erneut aktiviert werden. Entfernen Sie die Audiokonferenz-Lizenz des Benutzers, warten Sie ein paar Stunden, und weisen Sie die Lizenz erneut zu.  <br/> |01.03.2019  <br/> |
   
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
