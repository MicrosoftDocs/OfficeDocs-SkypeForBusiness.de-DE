---
title: Legacyzusammenführung – FQDN
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeFqdnPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: d72841ff-3c4d-4233-a933-f3a95d75d89b
ROBOTS: NOINDEX, NOFOLLOW
description: Der interne FQDN des Zugriffs-Edgepools wird für eine Vielzahl von Szenarien verwendet, in denen interne Benutzer mit externen Benutzern für Partnerverbund, Remotebenutzerzugriff und Verbindungen mit öffentlichen Chatdiensten kommunizieren. Wenn der Edgeserver mit Lastenausgleich in Ihrer Legacyumgebung bereitgestellt war, geben Sie den vollqualifizierten Domänennamen des internen Lastenausgleichsgeräts an.
ms.openlocfilehash: 25d366e963110e5f41e5fcc5787ef6c952784b99
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628967"
---
# <a name="legacy-merge-fqdn"></a>Legacyzusammenführung – FQDN
 
Der interne vollqualifizierte Domänenname des Zugriffs-Edgepools wird für eine Vielzahl von Szenarien verwendet, bei denen interne Benutzer mit externen Benutzern im Rahmen einer Verbundpartnerschaft, zum Zwecke des Remotebenutzerzugriffs und über Verbindungen mit öffentlichen Instant Messaging-Diensten kommunizieren. Wenn der Edgeserver mit Lastenausgleich in Ihrer Legacyumgebung bereitgestellt wurde, geben Sie den vollqualifizierten Domänennamen des internen Lastenausgleichsgeräts an.
  
Der Wert **5061** des internen SIP-Zugriffsports  ist der TCP-SIP-Standardport (Transmission Control Protocol) für die Kommunikation mit Clients, Legacy-Front-End-Pools und -Servern. Wenn der Standardwert nicht verwendet wurde, aktualisieren Sie den Wert des internen SIP-Zugriffsports.
  

