---
title: Legacyzusammenführung – FQDN
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Der interne FQDN des Zugriffs-Edgepools wird für eine Vielzahl von Szenarien verwendet, in denen interne Benutzer mit externen Benutzern für Partnerverbund, Remotebenutzerzugriff und Verbindungen mit öffentlichen Chatdiensten kommunizieren. Wenn der Edgeserver mit Lastenausgleich in Ihrer Legacyumgebung bereitgestellt war, geben Sie den vollqualifizierten Domänennamen des internen Lastenausgleichsgeräts an.'
---

# <a name="legacy-merge-fqdn"></a>Legacyzusammenführung – FQDN
 
Der interne vollqualifizierte Domänenname des Zugriffs-Edgepools wird für eine Vielzahl von Szenarien verwendet, bei denen interne Benutzer mit externen Benutzern im Rahmen einer Verbundpartnerschaft, zum Zwecke des Remotebenutzerzugriffs und über Verbindungen mit öffentlichen Instant Messaging-Diensten kommunizieren. Wenn der Edgeserver mit Lastenausgleich in Ihrer Legacyumgebung bereitgestellt wurde, geben Sie den vollqualifizierten Domänennamen des internen Lastenausgleichsgeräts an.
  
Der Wert **5061** des internen SIP-Zugriffsports  ist der TCP-SIP-Standardport (Transmission Control Protocol) für die Kommunikation mit Clients, Legacy-Front-End-Pools und -Servern. Wenn der Standardwert nicht verwendet wurde, aktualisieren Sie den Wert des internen SIP-Zugriffsports.
  

