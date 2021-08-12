---
title: Konfigurieren der Besprechungsteilnahmeseite in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Besprechungsteilnahmeseite in Skype for Business Server konfigurieren.'
ms.openlocfilehash: d1615b2d436cf884ee8d37e911b7ca82c57289973279c6f98f4360a6a40d99e0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54313223"
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
   

