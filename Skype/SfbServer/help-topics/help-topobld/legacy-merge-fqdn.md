---
title: Legacyzusammenführung – FQDN
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
- ms.lync.tb.LegacyMergeFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d72841ff-3c4d-4233-a933-f3a95d75d89b
description: Der interne FQDN des Zugriffs-Edgepools wird für eine Vielzahl von Szenarien verwendet, in denen interne Benutzer mit externen Benutzern für Partnerverbund, Remotebenutzerzugriff und Verbindungen mit öffentlichen Chatdiensten kommunizieren. Wenn der Edgeserver mit Lastenausgleich in Ihrer Legacyumgebung bereitgestellt war, geben Sie den vollqualifizierten Domänennamen des internen Lastenausgleichsgeräts an.
ms.openlocfilehash: b9c2e2977f2cfb579bc4c96d76d49883198a80a6901ba3e0fb0200b6c4704f6d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336925"
---
# <a name="legacy-merge-fqdn"></a>Legacyzusammenführung – FQDN
 
Der interne vollqualifizierte Domänenname des Zugriffs-Edgepools wird für eine Vielzahl von Szenarien verwendet, bei denen interne Benutzer mit externen Benutzern im Rahmen einer Verbundpartnerschaft, zum Zwecke des Remotebenutzerzugriffs und über Verbindungen mit öffentlichen Instant Messaging-Diensten kommunizieren. Wenn der Edgeserver mit Lastenausgleich in Ihrer Legacyumgebung bereitgestellt wurde, geben Sie den vollqualifizierten Domänennamen des internen Lastenausgleichsgeräts an.
  
Der Wert **5061** des internen SIP-Zugriffsports  ist der TCP-SIP-Standardport (Transmission Control Protocol) für die Kommunikation mit Clients, Legacy-Front-End-Pools und -Servern. Wenn der Standardwert nicht verwendet wurde, aktualisieren Sie den Wert des internen SIP-Zugriffsports.
  

