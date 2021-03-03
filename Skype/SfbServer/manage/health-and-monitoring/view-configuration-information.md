---
title: Anzeigen von Informationen zur Konfiguration von CdR in Skype for Business Server
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
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Aufzeichnung von Anrufdetail (Call Detail Recording, CDR) in Skype for Business Server verwenden.'
ms.openlocfilehash: 55e5e4e2f1b9d3d54ecb6a4a2614b2b1d206f2fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816635"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>Anzeigen von Informationen zur Konfiguration von CdR in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Aufzeichnung von Anrufdetails (Call Detail Recording, CDR) in Skype for Business Server verwenden.
  
Die Funktion zum Aufzeichnen von Kommunikationsdatensätzen (KDS) ermöglicht das Nachverfolgen von Peer-zu-Peer-, VoIP- und Konferenzanrufen. Diese Nutzungsdaten umfassen Informationen wie z. B. Anrufer, Angerufener, Anrufzeitpunkt und Anrufdauer.
  
Bei der Installation von Skype for Business Server wird eine einzelne, globale Auflistung von Konfigurationseinstellungen für die Zusammenstellung von CdR für Sie erstellt. Administratoren können darüber hinaus Auflistungen mit benutzerdefinierten Einstellungen erstellen, die auf die einzelnen Standorte angewendet werden können. Sie können die in Ihrer Organisation verwendeten Konfigurationseinstellungen für die KDS mithilfe der Skype for Business Server-Systemsteuerung oder des [Cmdlets "Get-CsCdrConfiguration"](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) anzeigen.
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>So zeigen Sie Konfigurationsinformationen für die CdR mithilfe der Skype for Business Server-Systemsteuerung an

1. Klicken Sie in der Skype for Business Server-Systemsteuerung **auf "Überwachung und Archivierung".**
    
2. Auf der Registerkarte **Aufzeichnung von Kommunikationsdatensätzen** wird eine Liste mit allen KDS-Konfigurationseinstellungen angezeigt; für jede Einstellungsauflistung wird der **Name** der Auflistung angezeigt; ob KDS aktiviert wurde oder nicht (die Eigenschaft **KDS**); und ob die Bereinigung (die Eigenschaft **Bereinigungsfunktion für aufgezeichnete Kommunikationsdatensätze**) aktiviert wurde oder nicht. Sie können detaillierte Informationen zu einer Auflistung anzeigen, indem Sie doppelt auf diese Auflistung klicken. Alternativ können Sie die gewünschte Auflistung auswählen und auf **Bearbeiten** und **Details anzeigen** klicken. Beachten Sie Folgendes: Es können jeweils nur detaillierte Informationen zu einer Auflistung mit KDS-Konfigurationseinstellungen angezeigt werden.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Informationen zur Konfiguration von CdR mithilfe Windows PowerShell Cmdlets

Sie können die Konfigurationseinstellungen für die CdR mithilfe von Windows PowerShell und dem cmdlet Get-CsCdrConfiguration anzeigen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell. Details zur Verwendung von Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Schnellstart: Verwalten von Microsoft Lync Server 2010 mithilfe von Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Prozess ist in Skype for Business Server identisch.
  
### <a name="to-view-cdr-configuration-information"></a>So zeigen Sie KDS-Konfigurationsinformationen an

- Geben Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE, um Informationen zu allen Konfigurationseinstellungen für die Mediendatenverwaltung (CDR) eins zu erhalten:
    
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

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Get-CsCdrConfiguration".](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)
  

