---
title: Verwalten von Einwahlkonferenzen in Skype for Business Server
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
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Einwahlkonferenzen in Skype for Business Server verwalten.'
ms.openlocfilehash: ba8b62456a1fa2024f2cf37642658e76d528ebf3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818576"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>Verwalten von Einwahlkonferenzen in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie Einwahlkonferenzen in Skype for Business Server verwalten.
  
In diesem Themenbereich wird die Verwaltung von Einwahlkonferenzen beschrieben. Weitere Informationen zum Planen und Konfigurieren von Einwahlkonferenzen bei der Bereitstellung finden Sie unter [Planen von Einwahlkonferenzen in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md) und [Konfigurieren von Einwahlkonferenzen in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
Sie können die folgenden Aufgaben ausführen, um Einwahlkonferenzen zu verwalten: Aktivieren oder Deaktivieren von Einwahlkonferenzen, Verwalten von Zugriffsnummern, Verwalten von PIN-Richtlinien für Einwahlkonferenzen, Verwalten von Konferenz Mitgliedschaften und hinterlassen von Ankündigungen, Ändern von Tastenzuordnungen für DTMF und Benutzer zur Einwahlkonferenz willkommen. 
  
Weitere Informationen zum Verwalten von Wählplänen finden Sie unter [erstellen oder Ändern eines Wählplans in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
Weitere Informationen zur PSTN-Verwendung finden Sie unter [Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in Skype for Business](../../deploy/deploy-enterprise-voice/voice-and-pstn.md).
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Verwalten von Einwahlkonferenzen mithilfe der Skype for Business Server-Systemsteuerung

So verwalten Sie Informationen über Einwahlkonferenzen:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenz**.
    
So verwalten Sie Informationen über Wähleinstellungen und die PSTN-Verwendung:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Verwalten von Einwahlkonferenzen mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie die folgenden Cmdlets, um Einwahlkonferenzen mithilfe der Skype for Business Server-Verwaltungsshell zu verwalten:
  
**Konfigurationseinstellungen für die Einwahl**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Gibt Informationen zu den Konferenzverzeichnissen zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind. Konferenzverzeichnisse helfen den Benutzern von Einwahlkonferenzen beim Suchen nach Konferenzinformationen.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Ruft Informationen dazu ab, wie Skype for Business Server antwortet, wenn Benutzer an einer Einwahlkonferenz teilnehmen oder diese hinterlassen.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Gibt Informationen über alle Zugriffsnummern für Einwahlkonferenzen zurück, die in Ihrer Organisation konfiguriert wurden.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Gibt die DTMF-Signaleinstellungen (Mehrfrequenzverfahren) zurück, die für Einwahlkonferenzen verwendet werden. Mit DTMF können Benutzer, die sich bei einer Konferenz einwählen, Konferenzeinstellungen mit der Telefontastatur steuern (z. B. eigene Person stummschalten bzw. Stummschaltung der eigenen Person aufheben oder Konferenz sperren bzw. entsperren).  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Gibt eine Liste der Sprachen zurück, die für die Verwendung mit Skype for Business Server-Einwahlkonferenzen unterstützt werden, einschließlich Regional-/Minderheitensprachen. Diese Sprachen werden für die Übermittlung von Audionachrichten und Anweisungen für Benutzer verwendet, die mit einem Telefon an der Konferenz teilnehmen.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Gibt Informationen zu den in Ihrer Organisation verwendeten Sätzen mit Wähleinstellungen zurück.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Weist einem oder mehreren Benutzern oder Gruppen einen Wählplan zu.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importiert Konferenzverzeichnisse von Microsoft Office Communications Server 2007 R2 in Skype for Business Server. Dadurch wird die Interoperabilität zwischen Skype for Business Server und Office Communications Server 2007 R2 gewährleistet.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Verschiebt ein vorhandenes Konferenzverzeichnis aus einem Pool in einen anderen.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Erstellt ein neues Konferenzverzeichnis für die Verwendung in Ihrer Organisation.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Erstellt eine neue Zugriffsnummer für Einwahlkonferenzen.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Erstellt eine neue Sammlung von Konfigurationseinstellungen für Einwahlkonferenzen. Diese Einstellungen legen fest, wie Skype for Business Server antwortet, wenn Benutzer an einer Einwahlkonferenz teilnehmen oder diese hinterlassen. Insbesondere werden Informationen darüber zurückgegeben, ob die Teilnehmer ihren Namen bei der Teilnahme an einer Konferenz aufzeichnen müssen, und wie (oder wenn) das System ankündigt, dass jemand dem Anruf beigetreten ist oder ihn verlassen hat.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |Erstellt eine neue Auflistung von DTMF-Signaleinstellungen (Dual-Tone Multifrequency, Mehrfrequenzverfahren), die für Einwahlkonferenzen verwendet werden.  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Erstellt einen neuen Wählplan.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Entfernt ein vorhandenes Konferenzverzeichnis.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Entfernt eine vorhandene Zugriffsnummer für Einwahlkonferenzen.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Entfernt eine oder mehrere Auflistungen von Konfigurationseinstellungen für Einwahlkonferenzen. Diese Einstellungen legen fest, wie Skype for Business Server antwortet, wenn Benutzer an einer Einwahlkonferenz teilnehmen oder diese hinterlassen.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Entfernt eine vorhandene Auflistung von DTMF-Signaleinstellungen (Dual Tone Multifrequency, Mehrfrequenzverfahren), die für Einwahlkonferenzen verwendet werden.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Ändert die Eigenschaftswerte einer vorhandenen Zugriffsnummer für Einwahlkonferenzen.  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Ändert Einstellungen, die bestimmen, wie Skype for Business Server antwortet, wenn Benutzer an einer Einwahlkonferenz teilnehmen oder diese hinterlassen.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Ändert die Einstellungen für die DTMF-Signalisierung (Dual-Tone Multifrequency, Mehrfrequenzverfahren), die für Einwahlkonferenzen verwendet werden.  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Ändert einen vorhandenen Wählplan.  <br/> |
   
**PIN-Richtlinieneinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Gibt Informationen zu den Client-PIN-Richtlinien zurück, die zur Verwendung in Ihrer Organisation konfiguriert sind. Die PIN-Authentifizierung ermöglicht Benutzern den Zugriff auf Skype for Business Server, indem eine PIN anstelle eines Benutzernamens und Kennworts bereitgestellt wird.  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Weist einem Benutzer oder einer Benutzergruppe eine Client-PIN-Richtlinie zu.  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Erstellt eine neue Client-PIN-Richtlinie (PIN: persönliche Identifikationsnummer).  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Entfernt die angegebene PIN-Richtlinie (persönliche Identifikationsnummer).  <br/> |
|[Satz-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Ändert eine oder mehrere vorhandene Clientrichtlinien für die persönliche Identifikationsnummer (PIN).  <br/> |
   

