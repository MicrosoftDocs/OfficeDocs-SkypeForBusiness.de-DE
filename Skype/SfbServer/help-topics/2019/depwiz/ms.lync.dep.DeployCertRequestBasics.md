---
title: Zertifikatsanforderung (Grundlagen)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
ROBOTS: NOINDEX, NOFOLLOW
description: Die Seite Name und Sicherheitseinstellungen enthält ein Textfeld zum Definieren eines Anzeigenamens, eine Dropdownliste für die Bit-Länge des Paars aus privatem und öffentlichem Schlüssel sowie ein Kontrollkästchen, mit dem Sie den privaten Schlüssel des Zertifikats als exportierbar kennzeichnen können.
ms.openlocfilehash: 4759b550c8e6aaa0c09b0ef44a6547ae3722a082
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273773"
---
# <a name="certificate-request-basic"></a>Zertifikatsanforderung (Grundlagen)
 
Die Seite **Name und Sicherheitseinstellungen** enthält ein Textfeld zum Definieren eines **Anzeigenamens**, eine Dropdownliste für die Bit- **Länge** des Paars aus privatem und öffentlichem Schlüssel sowie ein Kontrollkästchen, mit dem Sie **den privaten Schlüssel des Zertifikats als kennzeichnen können. exportierbar**.
  
Beim Anzeigenamen (oder einfachen Namen) eines Zertifikats handelt es sich um einen benutzerfreundlichen und problemlos identifizierbaren Namen für den Benutzer, der das Zertifikat anzeigt.
  
Für die Bitlänge des öffentlich-privaten Schlüsselpaars kann der Wert 1024, 2048 oder 4096 festgelegt werden.
  
Wenn Sie das Kontrollkästchen für **den privaten Schlüssel des Zertifikats als exportierbar kennzeichnen** aktivieren, können das Zertifikat und der private Schlüssel exportiert und auf einen anderen Computer oder Server verschoben werden. Dies ist nur erforderlich, wenn Sie einen Pool von Edgeserver für den Media Relay Authentication Service (MRAS) erstellen.
  
> [!CAUTION]
> Um die Sicherheit des Zertifikats und des Schlüsselpaars zu gewährleisten, sollten Sie nur dann den privaten Schlüssel des Zertifikats als exportierbar kennzeichnen auswählen, wenn dies unbedingt erforderlich ist. 
  

