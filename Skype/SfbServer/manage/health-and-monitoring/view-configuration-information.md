---
title: Anzeigen der CDR-Konfigurationsinformationen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie in Skype for Business Server die Verwendung der Anruf Detail Aufzeichnung (CDR) verwenden.'
ms.openlocfilehash: f4a216f1c2d8892370b80eef42c19cf07c133312
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817594"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>Anzeigen der CDR-Konfigurationsinformationen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie in Skype for Business Server die Verwendung der Anruf Detail Aufzeichnung (CDR) verwenden.
  
Die Funktion zum Aufzeichnen von Kommunikationsdatensätzen (KDS) ermöglicht das Nachverfolgen von Peer-to-Peer-, VoIP- und Konferenzanrufen. Diese Nutzungsdaten umfassen Informationen wie z. B. Anrufer, Angerufener, Anrufzeitpunkt und Anrufdauer.
  
Wenn Sie Skype for Business Server installieren, wird eine einzige globale Sammlung von CDR-Konfigurationseinstellungen für Sie erstellt. Administratoren haben außerdem die Möglichkeit, benutzerdefinierte Auflistungen von Einstellungen zu erstellen, die auf einzelne Standorte angewendet werden können. Mit der Skype for Business Server-Systemsteuerung oder dem Cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) können Sie die in Ihrer Organisation verwendeten CdR-Konfigurationseinstellungen anzeigen.
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>So zeigen Sie CDR-Konfigurationsinformationen mithilfe der Skype for Business Server-Systemsteuerung an

1. Klicken Sie in der Skype for Business Server-Systemsteuerung auf **Überwachung und Archivierung**.
    
2. Auf der Registerkarte **Aufzeichnung von Kommunikationsdatensätzen** wird eine Liste mit allen KDS-Konfigurationseinstellungen angezeigt; für jede Einstellungsauflistung wird der **Name** der Auflistung angezeigt; ob KDS aktiviert wurde oder nicht (die Eigenschaft **KDS**); und ob der Löschvorgang (die Eigenschaft **KDS-Löschvorgang**) aktiviert wurde oder nicht. Sie können detaillierte Informationen zu einer Auflistung anzeigen, indem Sie doppelt auf diese Auflistung klicken. Alternativ können Sie die gewünschte Auflistung auswählen und auf **Bearbeiten** und **Details anzeigen** klicken. Beachten Sie Folgendes: Es können jeweils nur detaillierte Informationen zu einer Auflistung mit KDS-Konfigurationseinstellungen angezeigt werden.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von CDR-Konfigurationsinformationen mithilfe von Windows PowerShell-Cmdlets

Sie können die CDR-Konfigurationseinstellungen mithilfe von Windows PowerShell und dem Cmdlet Get-CsCdrConfiguration anzeigen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-view-cdr-configuration-information"></a>So zeigen Sie KDS-Konfigurationsinformationen an

- Wenn Sie Informationen zu allen CdR-Konfigurationseinstellungen anzeigen möchten, geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    Es werden etwa folgende Informationen zurückgegeben:
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  

