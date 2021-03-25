---
title: Verwalten von Einwahlkonferenzen in Skype for Business Server
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
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: 'Zusammenfassung: Informationen zum Verwalten von Einwahlkonferenzen in Skype for Business Server.'
ms.openlocfilehash: 6bf5f13075b54d904ae70bc1b2106253442135db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119484"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>Verwalten von Einwahlkonferenzen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Einwahlkonferenzen in Skype for Business Server verwalten.
  
In diesem Thema wird das Verwalten von Einwahlkonferenzen beschrieben. Weitere Informationen zum Planen und Konfigurieren von Einwahlkonferenzen bei der Bereitstellung finden Sie unter [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md) und Configure [dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
Sie können die folgenden Aufgaben zum Verwalten von Einwahlkonferenzen ausführen: Aktivieren oder Deaktivieren von Einwahlkonferenzen, Verwalten von Zugriffsnummern, Verwalten von PIN-Richtlinien für Einwahlkonferenzen, Verwalten von Konferenzansagen und Verlassen von Ansagen, Ändern von Tastenzuordnungen für DTMF-Befehle und Willkommensbenutzer für Einwahlkonferenzen. 
  
Weitere Informationen zum Verwalten von Wählplänen finden Sie unter Erstellen oder Ändern [eines Wählplans in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
Weitere Informationen zur PSTN-Verwendung finden Sie unter [Configure voice policies, PSTN usage records, and voice routes in Skype for Business](../../deploy/deploy-enterprise-voice/voice-and-pstn.md).
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Verwalten von Einwahlkonferenzen mithilfe der Skype for Business Server-Systemsteuerung

So verwalten Sie Informationen zu Einwahlkonferenzen:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenz**.
    
So verwalten Sie Informationen zu Wählplänen und der PSTN-Verwendung:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Voicerouting**.
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Verwalten von Einwahlkonferenzen mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie die folgenden Cmdlets, um Einwahlkonferenzen mithilfe der Skype for Business Server-Verwaltungsshell zu verwalten:
  
**Einwahlkonfigurationseinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsConferenceDirectory](/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Gibt Informationen zu den Konferenzverzeichnissen zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind. Konferenzverzeichnisse helfen den Benutzern von Einwahlkonferenzen beim Suchen nach Konferenzinformationen.  <br/> |
|[Get-CsDialInConferencingConfiguration](/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Ruft Informationen dazu ab, wie Skype for Business Server reagiert, wenn Benutzer einer Einwahlkonferenz beitreten oder diese verlassen.  <br/> |
|[Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Gibt Informationen zu allen Zugriffsnummern für Einwahlkonferenzen zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Gibt die Für Einwahlkonferenzen verwendeten DTMF-Signaleinstellungen (Dual-Tone Multi-Frequency) zurück. Mit DTMF können Benutzer, die sich in eine Konferenz einwählen, die Konferenzeinstellungen steuern (z. B. stummschalten und deaktivieren oder die Konferenz sperren und entsperren), indem sie die Tastatur auf ihrem Telefon verwenden.  <br/> |
|[Get-CsDialInConferencingLanguageList](/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Gibt eine Liste der Sprachen zurück, einschließlich Regional-/Minderheitssprachen, die für die Verwendung mit Skype for Business Server-Einwahlkonferenzen unterstützt werden. Diese Sprachen werden für die Übermittlung von Audionachrichten und Anweisungen für Benutzer verwendet, die mit einem Telefon an der Konferenz teilnehmen.  <br/> |
|[Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Gibt Informationen zu den in Ihrer Organisation verwendeten Wählplänen zurück.  <br/> |
|[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Weist einem oder mehreren Benutzern oder Gruppen einen Wählplan zu.  <br/> |
|[Import-CsLegacyConferenceDirectory](/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importiert Konferenzverzeichnissen aus Microsoft Office Communications Server 2007 R2 in Skype for Business Server. Dadurch wird die Interoperabilität zwischen Skype for Business Server und Office Communications Server 2007 R2 ermöglicht.  <br/> |
|[Move-CsConferenceDirectory](/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Verschiebt ein vorhandenes Konferenzverzeichnis aus einem Pool in einen anderen.  <br/> |
|[New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Erstellt ein neues Konferenzverzeichnis für die Verwendung in Ihrer Organisation.  <br/> |
|[New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Erstellt eine neue Zugriffsnummer für Einwahlkonferenzen.  <br/> |
|[New-CsDialInConferencingConfiguration](/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Erstellt eine neue Auflistung von Konfigurationseinstellungen für Einwahlkonferenzen. Diese Einstellungen bestimmen, wie Skype for Business Server reagiert, wenn Benutzer einer Einwahlkonferenz beitreten oder diese verlassen. Insbesondere werden Informationen zurückgegeben, ob Teilnehmer ihren Namen bei der Teilnahme an einer Konferenz aufzeichnen müssen und wie (oder ob) das System ankündt, dass jemand dem Anruf beigetreten ist oder diesen verlassen hat.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |Erstellt eine neue Sammlung von DTMF-Signaleinstellungen (Dual-Tone Multi Frequency), die für Einwahlkonferenzen verwendet werden.  <br/> |
|[New-CsDialPlan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Erstellt einen neuen Wählplan.  <br/> |
|[Remove-CsConferenceDirectory](/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Entfernt ein vorhandenes Konferenzverzeichnis.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Entfernt eine vorhandene Zugriffsnummer für Einwahlkonferenzen.  <br/> |
|[Remove-CsDialInConferencingConfiguration](/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Entfernt eine oder mehrere Auflistungen von Konfigurationseinstellungen für Einwahlkonferenzen. Diese Einstellungen bestimmen, wie Skype for Business Server reagiert, wenn Benutzer einer Einwahlkonferenz beitreten oder diese verlassen.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Entfernt eine vorhandene Sammlung von DTMF-Signaleinstellungen (Dual-Tone Multi Frequency), die für Einwahlkonferenzen verwendet werden.  <br/> |
|[Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Ändert die Eigenschaftswerte einer vorhandenen Zugriffsnummer für Einwahlkonferenzen.  <br/> |
|[Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Ändert Einstellungen, die bestimmen, wie Skype for Business Server reagiert, wenn Benutzer einer Einwahlkonferenz beitreten oder diese verlassen.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Ändert die DtmF-Signaleinstellungen (Dual-Tone Multifrequency), die für Einwahlkonferenzen verwendet werden.  <br/> |
|[Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Ändert einen vorhandenen Wählplan.  <br/> |
   
**PIN-Richtlinieneinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Gibt Informationen zu den Client-PIN-Richtlinien zurück, die zur Verwendung in Ihrer Organisation konfiguriert sind. Die PIN-Authentifizierung ermöglicht Benutzern den Zugriff auf Skype for Business Server, indem sie anstelle eines Benutzernamens und Kennworts eine PIN bereitstellen.  <br/> |
|[Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Weist einem Benutzer oder einer Gruppe von Benutzern eine PIN -Richtlinie zu.  <br/> |
|[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Erstellt eine neue Client-PIN-Richtlinie (PIN: persönliche Identifikationsnummer).  <br/> |
|[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Entfernt die angegebene PIN-Richtlinie (persönliche Identifikationsnummer).  <br/> |
|[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Ändert eine oder mehrere vorhandene PIN-Richtlinien (Client Personal Identification Number).  <br/> |
