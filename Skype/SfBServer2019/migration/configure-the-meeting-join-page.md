---
title: Konfigurieren der Seite für den Besprechungsbeitritt
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn ein Benutzer in einer Besprechungsanfrage auf einen Besprechungslink klickt, erkennt die Seite "Besprechungsteilnahme", welcher Client bereits auf dem Computer des Benutzers installiert ist. Wenn ein Client bereits installiert ist, wird dieser Client geöffnet und der Besprechung beitreten. Wenn ein Client nicht installiert ist, wird die Web-App standardmäßig geöffnet.
ms.openlocfilehash: 1bab2dff25db94b36c41e5824401777006760bfc
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239326"
---
# <a name="configure-the-meeting-join-page"></a>Konfigurieren der Seite für den Besprechungsbeitritt

Wenn ein Benutzer in einer Besprechungsanfrage auf einen Besprechungslink klickt, erkennt die Seite "Besprechungsteilnahme", welcher Client bereits auf dem Computer des Benutzers installiert ist. Wenn ein Client bereits installiert ist, wird dieser Client geöffnet und der Besprechung beitreten. Wenn ein Client nicht installiert ist, wird die Web-App standardmäßig geöffnet.
  
Sie können das Verhalten der Besprechungsteilnahme Seite ändern, wenn Sie Benutzern die Teilnahme an Besprechungen gestatten möchten. Diese Konfigurationsoptionen wurden aus der Systemsteuerung entfernt, aber Sie werden mithilfe des CsWebServiceConfiguration-Cmdlets konfiguriert.
  
**CsWebServiceConfiguration-Parameter für Besprechungsteilnehmer Seite**

|**CsWebServiceConfiguration-Parameter**|**Beschreibung**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Wenn der Wert auf "true" festgelegt ist, wird Benutzern, die an einer Besprechung teilnehmen, mithilfe einer anderen Clientanwendung als lync die Möglichkeit gegeben, an der Besprechung teilzunehmen. Der Standardwert lautet "False".  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Wenn Sie auf "true" festgelegt ist, werden alternative Optionen für den Beitritt zu einer Onlinekonferenz automatisch erweitert und für die Benutzer angezeigt. Bei Festlegung auf "false" (der Standardwert) sind diese Optionen verfügbar, der Benutzer muss jedoch die Liste der Optionen für sich selbst anzeigen.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>So konfigurieren Sie die Seite "Besprechungsteilnahme" mithilfe der Skype for Business Server 2019-Verwaltungsshell

1. Starten Sie die Skype for Business Server 2019-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.
    
2. Führen Sie das folgende Cmdlet aus: 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    Dieses Cmdlet gibt die Konfigurationseinstellungen des Webdiensts zurück.
    
3. Führen Sie den folgenden Befehl aus, wobei die Parameter je nach ihrer Einstellung auf "true" oder "false" festgelegt sind (Einzelheiten zu den Parametern für dieses Cmdlet finden Sie in der Dokumentation zur [Skype for Business Server-Verwaltungsshell](../../SfbServer/manage/management-shell.md) ):
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


