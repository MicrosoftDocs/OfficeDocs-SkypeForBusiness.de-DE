---
title: Legacyzusammenführung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: Über den externen FQDN für Webkonferenzen können externe Benutzer an lokalen Besprechungen teilnehmen. Geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der externen Webkonferenzschnittstelle des Legacyedgeservers an.
ms.openlocfilehash: b49d8ed17bdc56050e00216c5506b85db2b1d3aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832995"
---
# <a name="legacy-merge"></a>Legacyzusammenführung

Über den externen FQDN für Webkonferenzen können externe Benutzer an lokalen Besprechungen teilnehmen. Geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der externen Webkonferenzschnittstelle des Legacyedgeservers an.

Der Wert **443** des externen Ports für externe Webkonferenzen ist der für Konferenzclients konfigurierte TCP-SIP-Standardport (Transmission Control Protocol) (Session Initiation Protocol). Wenn der Standardwert nicht verwendet wurde, aktualisieren Sie diesen Wert.

Aktivieren Sie das Kontrollkästchen **Dieser Edgepool wird für den Partnerverbund und die Verbindung mit öffentlichen Instant Messaging-Diensten verwendet**, wenn dieser Edgeserver für den Partnerverbund verwendet werden soll. Bei Bereitstellung mehrerer Edgeserver wird nur einer dieser Server für den Partnerverbund aktiviert. Wenn Sie dieses Kontrollkästchen nicht aktivieren und den Partnerverbund zu einem späteren Zeitpunkt aktivieren möchten, müssen Sie den Zusammenführungs-Assistenten des Topologie-Generators erneut ausführen und Ihre Topologie veröffentlichen. Ausführliche Informationen finden Sie unter [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).


