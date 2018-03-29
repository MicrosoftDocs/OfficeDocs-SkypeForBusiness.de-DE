---
title: Skype Room System – Vertrauenswürdige Domänen
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Lesen Sie dieses Thema und erfahren Sie, wie Sie vertrauenswürdige Domänen für Skype Room System und Skype for Business konfigurieren.
ms.openlocfilehash: 83d6e313f8643f593e1e25488e403da448649bd6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-trusted-domains"></a>Skype Room System – Vertrauenswürdige Domänen
 
Lesen Sie dieses Thema und erfahren Sie, wie Sie vertrauenswürdige Domänen für Skype Room System und Skype for Business konfigurieren.
  
## <a name="trusted-domains"></a>Vertrauenswürdige Domänen

Die Skype für Business Client zeigt ein Dialogfeld, mit dem Benutzer das Zertifikat aus der Skype für Business Server akzeptiert, wenn die SIP-Domäne des Benutzerkontos anmelden den Namen des Zertifikats im Betreff oder Antragstellername Alt präsentiert abweicht. Wenn das Zertifikat für Skype für Business Server in Ihrer Organisation konfigurierten keinen SIP-Domänenname des Skype Raum Systemkonto im Betreff oder Alt Antragstellername, müssen Sie diese Domänen auf das Zertifikat unter Vertrauenswürdige Domänen präsentiert konfigurieren. Registrierungsschlüssel auf dem Computer des Skype Raum System-Konsole. Skype Raum System Hersteller bereitgestellten Skype Raum vom Systemadministrator Handbuch wird erläutert, wie und wo in der Skype für Business Client vertrauenswürdigen Domänen hinzu. 
  
Nehmen wir beispielsweise an, dass die Zertifikate auf Skype für Business Server konfigurierten Betreff/Alt Antragstellernamen "CONTOSO. verfügen LOCAL"und eine der SIP-Domänen, die einem Benutzer für die Skype Raum System Anmeldeadresse zugewiesen ist"confrm1@contoso.net." Da contoso.net nicht in das Zertifikat auf dem Computer Skype Raum System ist, müssen Sie "contoso.local" als vertrauenswürdige Domäne in der Registrierung konfigurieren, wie in Ihrer Skype Raum System Hersteller bereitgestellten Skype Raum System-Administratorhandbuch erläutert. 
  

