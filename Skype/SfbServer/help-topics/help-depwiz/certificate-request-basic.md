---
title: Zertifikatsanforderung (Grundlagen)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
description: Die Seite Name und Sicherheitseinstellungen enthält ein Textfeld zum Definieren eines Anzeigenamens, eine Dropdownliste für die Bit-Länge des Paars aus privatem und öffentlichem Schlüssel sowie ein Kontrollkästchen, mit dem Sie den privaten Schlüssel des Zertifikats als exportierbar kennzeichnen können.
ms.openlocfilehash: e3ee374ad9a1fc29f67b7f756dcb2fd0384bcabc
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687788"
---
# <a name="certificate-request-basic"></a>Zertifikatsanforderung (Grundlagen)
 
Die Seite **Name und Sicherheitseinstellungen** enthält ein Textfeld zum Definieren eines **Anzeigenamens**, eine Dropdownliste für die Bit- **Länge** des Paars aus privatem und öffentlichem Schlüssel sowie ein Kontrollkästchen, mit dem Sie **den privaten Schlüssel des Zertifikats als exportierbar kennzeichnen**können.
  
Beim Anzeigenamen (oder einfachen Namen) eines Zertifikats handelt es sich um einen benutzerfreundlichen und problemlos identifizierbaren Namen für den Benutzer, der das Zertifikat anzeigt.
  
Für die Bitlänge des öffentlich-privaten Schlüsselpaars kann der Wert 1024, 2048 oder 4096 festgelegt werden.
  
Wenn Sie das Kontrollkästchen für **den privaten Schlüssel des Zertifikats als exportierbar kennzeichnen** aktivieren, können das Zertifikat und der private Schlüssel exportiert und auf einen anderen Computer oder Server verschoben werden. Dies ist nur erforderlich, wenn Sie einen Pool von Edgeserver für den Media Relay Authentication Service (MRAS) erstellen.
  
> [!CAUTION]
> Um die Sicherheit des Zertifikats und des Schlüsselpaars zu gewährleisten, sollten Sie nur dann den privaten Schlüssel des Zertifikats als exportierbar kennzeichnen auswählen, wenn dies unbedingt erforderlich ist. 
  

