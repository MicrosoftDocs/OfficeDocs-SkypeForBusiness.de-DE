---
title: Konfigurieren die Besprechung teilnehmen Seite in Skype für Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Zusammenfassung: Informationen zum Konfigurieren der Besprechung teilnehmen Seite in Skype für Business Server 2015.'
ms.openlocfilehash: c0b3ed39fc2f7a1a48635353cc1db673a4bd1cd5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server-2015"></a>Konfigurieren die Besprechung teilnehmen Seite in Skype für Business Server 2015
 
**Zusammenfassung:** Informationen zum Konfigurieren der Besprechung teilnehmen Seite in Skype für Business Server 2015.
  
Wenn ein Benutzer klickt einen Link zur Besprechung in eine Besprechungsanfrage an der Besprechung teilnehmen Seite erkennt, ob ein Skype für Business-Client bereits auf dem Computer des Benutzers installiert ist. Wenn ein Client bereits installiert ist, wird der Client wird geöffnet und der Besprechung teilnimmt. Ein Client nicht installiert ist, wird von standardmäßig die 2015 Version von Skype für Business-Client geöffnet. 
  
## <a name="configure-the-meeting-join-page"></a>Konfigurieren die Besprechung teilnehmen-Seite

Sie können das Verhalten der Teilnahme an einer Besprechung ändern Seite, wenn Sie Benutzer zur Teilnahme an Besprechungen mit anderen Versionen des Clients zulassen möchten. Diese Konfigurationsoptionen aus der Skype Business Server-Systemsteuerung entfernt wurden, aber Sie mit dem Cmdlet "Set-cswebserviceconfiguration" konfigurieren.
  
**Besprechung teilnehmen Seite Set-CsWebServiceConfiguration-Parameter**

|**Set-CsWebServiceConfiguration-parameter**|**Beschreibung**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Dieser Parameter ist für die Verwendung mit der lokalen Version von Skype für Business Server 2015 veraltet.  <br/> Bei auf True festgelegt, teilnehmen an einer Besprechung mithilfe einer anderen Clientanwendung als Benutzer Skype für Unternehmen Teilnahme an der Besprechung mithilfe ihrer aktuellen Clientanwendung Gelegenheit sein wird. Der Standardwert ist "False".  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Dieser Parameter ist für die Verwendung mit der lokalen Version von Skype für Business Server 2015 veraltet.  <br/>  Wenn Sie True festlegen, alternative Optionen für die Teilnahme an einer Konferenz online automatisch erweitert und anschließend den Benutzern angezeigt werden. Wenn auf False (Standardwert) gesetzt, diese Optionen zur Verfügung, aber der Benutzer die Liste der Optionen für sich selbst anzuzeigen muss.  <br/> |
   

