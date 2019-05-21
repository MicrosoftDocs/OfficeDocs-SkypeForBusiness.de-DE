---
title: Überprüfen der Konfigurationseinstellungen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie können die Replikation von Konfigurationsinformationen auf dem Edgeserver überprüfen, indem Sie das Cmdlet "Skype for Business Server 2019 Get-CsManagementStoreReplicationStatus" auf dem internen Computer ausführen, auf dem sich der zentrale Verwaltungsspeicher befindet, oder auf einem beliebigen der Computer, auf dem die Skype for Business Server 2019-Core-Komponenten (OcsCore. msi) installiert sind.
ms.openlocfilehash: 0ea966652972a97dac3e807cef42ddeaa5136322
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307035"
---
# <a name="verify-configuration-settings"></a>Überprüfen der Konfigurationseinstellungen

Sie können die Replikation von Konfigurationsinformationen auf dem Edgeserver überprüfen, indem Sie das Cmdlet "Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** " auf dem internen Computer ausführen, auf dem sich der zentrale Verwaltungsspeicher befindet, oder auf einem beliebigen Computer, auf dem die Skype for Business Server 2019-Core-Komponenten (OcsCore. msi) installiert sind. 
  
Anfängliche Ergebnisse können den Status "falsch" anstelle von "true" für die Replikation angeben. Wenn dies der Fall ist, führen Sie das Cmdlet **Invoke-CsManagementStoreReplication** aus, und lassen Sie die Replikation Zeit, bevor **Sie die Get-CsManagementStoreReplicationStatus** erneut ausführen. 
  

