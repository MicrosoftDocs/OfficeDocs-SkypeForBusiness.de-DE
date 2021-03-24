---
title: Anzeigen von Informationen zur CdR-Konfiguration in Skype for Business Server
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
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Aufzeichnung von Anrufdetails (Call Detail Recording, CDR) in Skype for Business Server verwenden.'
ms.openlocfilehash: fb832a3e0fcde7500b0516fb9a9672ab228d47ae
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098901"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>Anzeigen von Informationen zur CdR-Konfiguration in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Aufzeichnung von Anrufdetails (Call Detail Recording, CDR) in Skype for Business Server verwenden.
  
Die Funktion zum Aufzeichnen von Kommunikationsdatensätzen (KDS) ermöglicht das Nachverfolgen von Peer-zu-Peer-, VoIP- und Konferenzanrufen. Diese Nutzungsdaten umfassen Informationen wie z. B. Anrufer, Angerufener, Anrufzeitpunkt und Anrufdauer.
  
Wenn Sie Skype for Business Server installieren, wird eine einzelne, globale Auflistung von Konfigurationseinstellungen für cdR für Sie erstellt. Administratoren können darüber hinaus Auflistungen mit benutzerdefinierten Einstellungen erstellen, die auf die einzelnen Standorte angewendet werden können. Sie können die in Ihrer Organisation verwendeten CdR-Konfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung oder des [Cmdlets Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) anzeigen.
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>So zeigen Sie Konfigurationsinformationen für cdR mithilfe der Skype for Business Server-Systemsteuerung an

1. Klicken Sie in der Skype for Business Server-Systemsteuerung **auf Überwachung und Archivierung.**
    
2. Auf der Registerkarte **Aufzeichnung von Kommunikationsdatensätzen** wird eine Liste mit allen KDS-Konfigurationseinstellungen angezeigt; für jede Einstellungsauflistung wird der **Name** der Auflistung angezeigt; ob KDS aktiviert wurde oder nicht (die Eigenschaft **KDS**); und ob die Bereinigung (die Eigenschaft **Bereinigungsfunktion für aufgezeichnete Kommunikationsdatensätze**) aktiviert wurde oder nicht. Sie können detaillierte Informationen zu einer Auflistung anzeigen, indem Sie doppelt auf diese Auflistung klicken. Alternativ können Sie die gewünschte Auflistung auswählen und auf **Bearbeiten** und **Details anzeigen** klicken. Beachten Sie Folgendes: Es können jeweils nur detaillierte Informationen zu einer Auflistung mit KDS-Konfigurationseinstellungen angezeigt werden.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von CdR-Konfigurationsinformationen mithilfe Windows PowerShell Cmdlets

Sie können die Konfigurationseinstellungen für cdR mithilfe von Windows PowerShell und dem cmdlet Get-CsCdrConfiguration anzeigen. Sie können dieses Cmdlet entweder über die Skype for Business Server Management Shell oder über eine Remotesitzung von Windows PowerShell. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-view-cdr-configuration-information"></a>So zeigen Sie KDS-Konfigurationsinformationen an

- Geben Sie den folgenden Befehl in die Skype for Business Server-Verwaltungsshell ein, um Informationen zu allen Konfigurationseinstellungen für cdR eins zu erhalten, und drücken Sie dann die EINGABETASTE:
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

Weitere Informationen finden Sie im Hilfethema für das [Cmdlet Get-CsCdrConfiguration.](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)
