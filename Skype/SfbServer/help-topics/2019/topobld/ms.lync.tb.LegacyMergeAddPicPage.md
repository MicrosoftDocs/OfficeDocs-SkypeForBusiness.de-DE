---
title: Legacyzusammenführung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: Der externe FQDN Webkonferenzen ermöglicht externe Benutzern lokale-Besprechungen teilnehmen. Geben Sie den vollqualifizierten Domänennamen (FQDN) der Web Conferencing externen Schnittstelle der Edgeserver der Vorversion.
ms.openlocfilehash: 3e426af0b08660eaef619d4fd9cec9da2ca11b32
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919752"
---
# <a name="legacy-merge"></a>Legacyzusammenführung

Den **externen FQDN Webkonferenzen** ermöglicht externe Benutzern lokale-Besprechungen teilnehmen. Geben Sie den vollqualifizierten Domänennamen (FQDN) der Web Conferencing externen Schnittstelle der Edgeserver der Vorversion.

Der Wert für die **Externe Webkonferenzen externer Port** **443** ist das Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) Standardport für Live Meeting-Clients konfiguriert sind. Wenn der Standardwert nicht verwendet wurde, aktualisieren Sie den Wert für **Externe Webkonferenzen externer Port** .

Aktivieren Sie das Kontrollkästchen **dieser Edge-Pool für den Verbund und öffentliches Instant Messaging-Diensten verwendet wird** , wenn Sie diesen Edgeserver für den Verbund verwenden möchten. Wenn Sie mehrere Edgeserver bereitgestellt haben, wird nur eine von ihnen für den Verbund aktiviert werden. Wenn Sie nicht aktivieren Sie dieses Kontrollkästchen, und Sie später entscheiden, dass Sie einen Verbund einrichten möchten, müssen Sie den Topologie-Generator Seriendruck-Assistenten erneut ausführen, sowie Veröffentlichen Ihrer Topologie. Weitere Informationen hierzu finden Sie unter [Phase 4: Zusammenführen von Topologien](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).


