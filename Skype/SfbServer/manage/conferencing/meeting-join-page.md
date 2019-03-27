---
title: Konfigurieren die Besprechung teilnehmen Seite in Skype für Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Zusammenfassung: Informationen zum Konfigurieren der Besprechung teilnehmen Seite in Skype für Business Server.'
ms.openlocfilehash: 4f737bdab0586cb342d1271f348cf765ae093c5c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875546"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>Konfigurieren die Besprechung teilnehmen Seite in Skype für Business Server
 
**Zusammenfassung:** Informationen zum Konfigurieren der Besprechung teilnehmen Seite in Skype für Business Server.
  
Wenn ein Benutzer klickt einen Link zur Besprechung in eine Besprechungsanfrage an der Besprechung teilnehmen Seite erkennt, ob ein Skype für Business-Client bereits auf dem Computer des Benutzers installiert ist. Wenn ein Client bereits installiert ist, wird der Client wird geöffnet und der Besprechung teilnimmt. Wenn ein Client nicht installiert ist, öffnet standardmäßig die Skype für Business Client. 
  
## <a name="configure-the-meeting-join-page"></a>Konfigurieren der Seite für den Besprechungsbeitritt

Sie können das Verhalten der Teilnahme an einer Besprechung ändern Seite, wenn Sie Benutzer zur Teilnahme an Besprechungen mit anderen Versionen des Clients zulassen möchten. Diese Konfigurationsoptionen aus der Skype Business Server-Systemsteuerung entfernt wurden, aber Sie mit dem Cmdlet "Set-cswebserviceconfiguration" konfigurieren.
  
**Besprechung teilnehmen Seite Set-CsWebServiceConfiguration-Parameter**

|**Set-CsWebServiceConfiguration-parameter**|**Beschreibung**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Dieser Parameter ist für die Verwendung mit der lokalen Version von Skype für Business Server veraltet.  <br/> Bei auf True festgelegt, teilnehmen an einer Besprechung mithilfe einer anderen Clientanwendung als Benutzer Skype für Unternehmen Teilnahme an der Besprechung mithilfe ihrer aktuellen Clientanwendung Gelegenheit sein wird. Der Standardwert lautet "False".  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Dieser Parameter ist für die Verwendung mit der lokalen Version von Skype für Business Server veraltet.  <br/>  Wenn Sie True festlegen, alternative Optionen für die Teilnahme an einer Konferenz online automatisch erweitert und anschließend den Benutzern angezeigt werden. Wenn auf False (Standardwert) gesetzt, diese Optionen zur Verfügung, aber der Benutzer die Liste der Optionen für sich selbst anzuzeigen muss.  <br/> |
   

