---
title: Konfigurieren der Besprechungsteilnahmeseite in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Besprechungsteilnahmeseite in Skype for Business Server konfigurieren.'
ms.openlocfilehash: 39a9fd42fd7d1017ece572856f6d85a09e1f55fe
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743561"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>Konfigurieren der Besprechungsteilnahmeseite in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Besprechungsteilnahmeseite in Skype for Business Server konfigurieren.
  
Wenn ein Benutzer in einer Besprechungsanfrage auf einen Besprechungslink klickt, erkennt die Seite für den Besprechungsbeitritt, ob ein Skype for Business Client bereits auf dem Computer des Benutzers installiert ist. Wenn bereits ein Client installiert ist, wird dieser geöffnet und tritt der Besprechung bei. Wenn kein Client installiert ist, wird standardmäßig der Skype for Business Client geöffnet. 
  
## <a name="configure-the-meeting-join-page"></a>Konfigurieren der Seite für den Besprechungsbeitritt

Sie können das Verhalten der Seite für den Besprechungsbeitritt ändern, wenn Sie Benutzern die Teilnahme an Besprechungen mit anderen Versionen des Clients gestatten möchten. Diese Konfigurationsoptionen wurden aus der Skype for Business Server Systemsteuerung entfernt, aber Sie konfigurieren sie mithilfe des Cmdlets Set-CsWebServiceConfiguration.
  
**Parameter für Set-CsWebServiceConfiguration Seite "Besprechungsteilnahme"**

|**Set-CsWebServiceConfiguration-Parameter**|**Beschreibung**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Dieser Parameter ist für die Verwendung mit der lokalen Version von Skype for Business Server veraltet.  <br/> Bei Festlegung auf "True" erhalten Benutzer, die mithilfe einer anderen Clientanwendung als Skype for Business an einer Besprechung teilnehmen, die Möglichkeit, mithilfe ihrer aktuellen Clientanwendung an der Besprechung teilzunehmen. Der Standardwert lautet "False".  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Dieser Parameter ist für die Verwendung mit der lokalen Version von Skype for Business Server veraltet.  <br/>  Bei Festlegung auf "True" werden alternative Optionen für die Teilnahme an einer Onlinekonferenz automatisch erweitert und Benutzern angezeigt. Bei Festlegung auf "False" (Standardwert) sind diese Optionen verfügbar, aber der Benutzer muss die Liste der Optionen für sich selbst anzeigen.  <br/> |
   

