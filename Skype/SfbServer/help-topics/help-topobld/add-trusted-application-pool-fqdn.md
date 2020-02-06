---
title: Hinzufügen des FQDN des vertrauenswürdigen Anwendungspools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 'Wenn Sie einen vertrauenswürdigen Anwendungspool vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) definieren möchten, geben Sie Folgendes an:'
ms.openlocfilehash: 5dcf5317c3234db310ed7b80bca6403190690348
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820567"
---
# <a name="add-trusted-application-pool-fqdn"></a>Hinzufügen des FQDN des vertrauenswürdigen Anwendungspools
 
Wenn Sie einen vertrauenswürdigen Anwendungspool vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) definieren möchten, geben Sie Folgendes an:
  
Ein FQDN des Servers oder Pools von Servern, auf dem die vertrauenswürdigen Anwendungen gehostet werden.
  
Wählen Sie den Pool für **mehrere Computer** aus, wenn Sie einen Pool von Servern für die vertrauenswürdigen Anwendungen überlasten Ausgleich und hohe Verfügbarkeit bereitstellen, oder wählen Sie einen **einzelnen Computerpool** aus, wenn Sie keinen Lastenausgleich oder hohe Verfügbarkeit benötigen.
  
> [!IMPORTANT]
> Ein einzelner Trusted Applications-Server kann später nicht in einen Pool von Servern konvertiert werden. Wenn Sie der Meinung sind, dass Sie in Zukunft einen Pool benötigen, können Sie einen mehr Serverpool mit einem einzelnen Computer bereitstellen und bei Bedarf Server hinzufügen. 
  
Details zu vertrauenswürdigen Anwendungspools finden Sie unter [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
  

