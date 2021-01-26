---
title: Konfigurieren der Seite für den Besprechungs beitritt in Skype for Business Server
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
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Seite für den Besprechungs beitritt in Skype for Business Server konfigurieren.'
ms.openlocfilehash: 247664a3ff4bbc4ee055775d26f1d077b662752b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828035"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>Konfigurieren der Seite für den Besprechungs beitritt in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Seite für den Besprechungs beitritt in Skype for Business Server konfigurieren.
  
Wenn ein Benutzer auf einen Besprechungslink in einer Besprechungsanfrage klickt, erkennt die Seite für den Besprechungsteil nehmen, ob bereits ein Skype for Business-Client auf dem Computer des Benutzers installiert ist. Wenn bereits ein Client installiert ist, wird dieser geöffnet und tritt der Besprechung bei. Wenn kein Client installiert ist, wird standardmäßig der Skype for Business-Client geöffnet. 
  
## <a name="configure-the-meeting-join-page"></a>Konfigurieren der Seite für den Besprechungsbeitritt

Sie können das Verhalten der Seite für den Besprechungs beitritt ändern, wenn Sie Benutzern die Teilnahme an Besprechungen mit anderen Versionen des Clients ermöglichen möchten. Diese Konfigurationsoptionen wurden aus der Skype for Business Server-Systemsteuerung entfernt, aber Sie konfigurieren sie mithilfe des Set-CsWebServiceConfiguration Cmdlets.
  
**Parameter für die Seite "BesprechungsSet-CsWebServiceConfiguration teilnehmen**

|**Parameter "Set-CsWebServiceConfiguration"**|**Beschreibung**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Dieser Parameter ist für die Verwendung mit der lokalen Version von Skype for Business Server veraltet.  <br/> Bei "True" können Benutzer, die über eine andere Clientanwendung als Skype for Business an einer Besprechung teilnehmen, über ihre aktuelle Clientanwendung an der Besprechung teilnehmen. Der Standardwert lautet "False".  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Dieser Parameter ist für die Verwendung mit der lokalen Version von Skype for Business Server veraltet.  <br/>  Bei "True" werden alternative Optionen für den Beitritt zu einer Onlinekonferenz automatisch erweitert und benutzern angezeigt. Bei "False" (Standardwert) sind diese Optionen verfügbar, aber der Benutzer muss die Liste der Optionen für sich selbst anzeigen.  <br/> |
   

