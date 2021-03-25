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
description: 'Hier erhalten Sie eine Liste der bekannten Probleme bei der Verwendung von Microsoft als Anbieter von Einwahlkonferenzen, Status und einige Problemumgehungen. '
ms.openlocfilehash: 13c493e16e5a6fef8b93b80d2a0e706f8f222ffa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111961"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Problembehandlung und bekannte Probleme bei Audiokonferenzen

 **Dieser Artikel gilt für Skype for Business-Benutzer, die Microsoft als Audiokonferenzanbieter verwenden. Dies gilt nicht für Kunden, die einen Drittanbieter für Audiokonferenzen (ACP) verwenden.**
  
## <a name="troubleshooting-and-known-issues"></a>Problembehandlung und bekannte Probleme

Audiokonferenzen, die Microsoft als Audiokonferenzanbieter verwenden, haben aktuelle Probleme, die nachverfolgt und aktiv untersucht werden und möglicherweise behoben werden, wenn das Feature in zukünftigen Versionen von Microsoft 365 aktualisiert wird.
  
Verwenden Sie dies vorerst als Referenz, wenn Sie potenzielle Probleme beim Einrichten und Arbeiten von Audiokonferenzen für die Personen, die Skype for Business in Ihrer Organisation verwenden, beheben möchten.

|**Problem**|**Verhalten/Symptome**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Benachrichtigungen bei Zu- oder Abgang sind zu Beginn einer Besprechung aktiviert, werden aber kurz darauf deaktiviert.  <br/> |Die Benachrichtigungen bei Zu- oder Abgang sind für Besprechungen, an denen Teilnehmer sowohl über Skype for Business-Apps als auch per Einwahl teilnehmen, standardmäßig deaktiviert. Sie können die Ankündigungen in den **Skype-Besprechungsoptionen** in der Skype for Business-App aktivieren. Bei einer Besprechung, an der alle Teilnehmer durch Einwahl teilnehmen, sind die Benachrichtigungen bei Zu- oder Abgang standardmäßig aktiviert, da den Teilnehmern keine Teilnehmerliste zur Verfügung steht. Wenn eine Besprechung ausschließlich mit Teilnehmern begonnen hat, die durch Einwahl teilnehmen, werden die Benachrichtigungen bei Zu- oder Abgang aktiviert. Wenn jedoch ein Teilnehmer über eine Skype for Business-App teilnimmt, werden die Benachrichtigungen deaktiviert. Deaktivierte Benachrichtigungen können mithilfe der **Skype-Besprechungsoptionen** in der Skype for Business-App wieder aktiviert werden. <br/> |Keine Problemumgehung  <br/> |30.8.2017  <br/> |
|Wenn ein Benutzer durch Zuweisen einer E5-Lizenz erstmals bereitgestellt wird und das Postfach nicht aktiviert ist, wird die Begrüßungs-E-Mail für Audiokonferenzen möglicherweise nicht zugestellt.  <br/> |In diesem Fall können Sie die Informationen zur Audiokonferenz jederzeit mit der Option **Audio conferencing** (Audiokonferenz) im Skype for Business Admin Center oder mit PowerShell erneut an den Benutzer senden. Weitere Informationen finden Sie unter Aktivieren oder Deaktivieren des Sendens von [E-Mails, wenn sich die Einstellungen für Audiokonferenzen ändern.](enable-or-disable-sending-emails-when-their-settings-change.md)  <br/> **Hinweis:** Um die PIN für Audiokonferenzen erneut an den Benutzer zu senden, muss die PIN zurückgesetzt werden. Dies kann auch mithilfe von **Audiokonferenzen** im Skype for Business Admin Center oder mithilfe von PowerShell geschehen.          |Keine Problemumgehung  <br/> |30.8.2017  <br/> |
|Es kann bis zu 24 Stunden dauern, bis Audiokonferenzanrufe in den Nutzungsberichten angezeigt werden.  <br/> |Für diesen Bereich sind in zukünftigen Dienstupdates Verbesserungen geplant.  <br/> |Keine Problemumgehung  <br/> |30.8.2017  <br/> |
|Wenn sich ein Anrufer in eine Konferenzbrücke einwählt, nachdem die Besprechung von einem Skype for Business-Benutzer gesperrt wurde, wird in derSkype for Business-App keine Benachrichtigung dazu angezeigt, dass der Benutzer im Wartebereich wartet.  <br/> |Dies ist zurzeit entwurfsbedingt, wir werden jedoch Ihr Feedback hinsichtlich der Unterstützung dieser Funktion in zukünftigen Dienstupdates berücksichtigen.  <br/> |Keine Problemumgehung  <br/> |30.8.2017  <br/> |
|Ein Skype for Business Server(on-prem)-Benutzer, dem vor dem 1. März 2019 die Lizenz für Audiokonferenzen zugewiesen wurde, sieht möglicherweise die Einwahlkoordinaten in seinen Besprechungseinlämmungen nicht.  <br/> |Die Bereitstellung von Skype for Business Server-Benutzern für Teams Audio conferencing wurde bis zu diesem Datum nicht unterstützt. Sie wird jetzt unterstützt und ist eine Komponente von ["Besprechungen zuerst".](/microsoftteams/meetings-first) Der Benutzer muss über eine Teams-Lizenz verfügen.  <br/> |Die Bereitstellungspipeline muss reaktiviert werden. Entfernen Sie die Lizenz für Audiokonferenzen des Benutzers, warten Sie einige Stunden, undzuweisen Sie die Lizenz erneut.  <br/> |01.03.2019  <br/> |
   
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)