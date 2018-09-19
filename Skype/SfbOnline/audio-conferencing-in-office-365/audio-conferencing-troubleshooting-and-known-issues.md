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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Rufen Sie eine Liste bekannter Probleme bei Verwendung von Microsoft als Anbieternamens einwahlkonferenz, Status und umgangen. '
ms.openlocfilehash: 997cc5007df35b307cb714b891bc60764bd4a645
ms.sourcegitcommit: d21e7ef1d4e36f4aced606e11837c693e8fd6410
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "23999174"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Problembehandlung und bekannte Probleme bei Audiokonferenzen

 **Dieser Artikel ist für Skype für Unternehmensbenutzer, die mit Microsoft als Anbieter von Audiokonferenzen. Es gilt nicht für Kunden, die einen Drittanbieter-Audiokonferenzen (ACP) verwenden.**
  
## <a name="troubleshooting-and-known-issues"></a>Problembehandlung und bekannte Probleme

Bei Audiokonferenzen mit Microsoft als Audiokonferenzanbieter sind aktuelle Probleme bekannt, die nachverfolgt, aktiv untersucht und potentiell gelöst werden, wenn die Funktion in zukünftigen Versionen von Office 365 aktualisiert wird.
  
In dieser Übung verwenden Sie dies als einen Verweis bei der Problembehandlung potenzielle Probleme mit dem Einrichten von Audiokonferenzen abrufen und für die Verwendung von Skype für Unternehmen in Ihrer Organisation Personen arbeiten.

|**Problem**|**Verhalten/Symptome**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Benachrichtigungen bei Zu- oder Abgang sind zu Beginn einer Besprechung aktiviert, werden aber kurz darauf deaktiviert.  <br/> |Die Benachrichtigungen bei Zu- oder Abgang sind für Besprechungen, an denen Teilnehmer sowohl über Skype for Business-Apps als auch per Einwahl teilnehmen, standardmäßig deaktiviert. Sie können die Ankündigungen in den **Skype-Besprechungsoptionen** in der Skype for Business-App aktivieren. Bei einer Besprechung, an der alle Teilnehmer durch Einwahl teilnehmen, sind die Benachrichtigungen bei Zu- oder Abgang standardmäßig aktiviert, da den Teilnehmern keine Teilnehmerliste zur Verfügung steht. Wenn eine Besprechung ausschließlich mit Teilnehmern begonnen hat, die durch Einwahl teilnehmen, werden die Benachrichtigungen bei Zu- oder Abgang aktiviert. Wenn jedoch ein Teilnehmer über eine Skype for Business-App teilnimmt, werden die Benachrichtigungen deaktiviert. Deaktivierte Benachrichtigungen können mithilfe der **Skype-Besprechungsoptionen** in der Skype for Business-App wieder aktiviert werden. <br/> |Keine Problemumgehung  <br/> |30.8.2017  <br/> |
|Wenn ein Benutzer durch Zuweisen einer E5-Lizenz erstmals bereitgestellt wird und das Postfach nicht aktiviert ist, wird die Begrüßungs-E-Mail für Audiokonferenzen möglicherweise nicht zugestellt.  <br/> |In diesem Fall können Sie die Informationen zur Audiokonferenz jederzeit mit der Option **Audio conferencing** (Audiokonferenz) im Skype for Business Admin Center oder mit PowerShell erneut an den Benutzer senden. Finden Sie unter [Aktivieren oder deaktivieren Sie e-Mails senden, wenn Audiokonferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-their-settings-change.md).  <br/> **Hinweis:** Um dem Benutzer die Audiokonferenz PIN erneut zu senden, muss die PIN zurückgesetzt werden. Dies kann auch über die Option **Audio conferencing** (Audiokonferenz) im Skype for Business Admin Center oder mithilfe von PowerShell geschehen.          |Keine Problemumgehung  <br/> |30.8.2017  <br/> |
|Es kann bis zu 24 Stunden dauern, bis Audiokonferenzanrufe in den Nutzungsberichten angezeigt werden.  <br/> |Für diesen Bereich sind in zukünftigen Dienstupdates Verbesserungen geplant.  <br/> |Keine Problemumgehung  <br/> |30.8.2017  <br/> |
|Wenn sich ein Anrufer in eine Konferenzbrücke einwählt, nachdem die Besprechung von einem Skype for Business-Benutzer gesperrt wurde, wird in derSkype for Business-App keine Benachrichtigung dazu angezeigt, dass der Benutzer im Wartebereich wartet.  <br/> |Dies ist zurzeit entwurfsbedingt, wir werden jedoch Ihr Feedback hinsichtlich der Unterstützung dieser Funktion in zukünftigen Dienstupdates berücksichtigen.  <br/> |Keine Problemumgehung  <br/> |30.8.2017  <br/> |
   
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Erwerben von Audiokonferenzen in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
