---
title: Verwalten von Einwahlkonferenzen in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: 'Zusammenfassung: Informationen Sie zum Verwalten von einwahlkonferenzen in Skype für Business Server 2015.'
ms.openlocfilehash: 44427a9109fd061233d1c8676166788e162c7e08
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server-2015"></a>Verwalten von Einwahlkonferenzen in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zum Verwalten von einwahlkonferenzen in Skype für Business Server 2015.
  
In diesem Themenbereich wird die Verwaltung von Einwahlkonferenzen beschrieben. Weitere Informationen zum Planen und Konfigurieren von einwahlkonferenzen bei der Bereitstellung finden Sie unter [Planen von einwahlkonferenzen in Skype für Business Server 2015](../../plan-your-deployment/conferencing/dial-in-conferencing.md) und [Configure einwahlkonferenzen in Skype für Business Server 2015](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
Sie können die folgenden Aufgaben zum Verwalten von einwahlkonferenzen ausführen: Aktivieren oder Deaktivieren von einwahlkonferenzen, Zugriffsnummern verwalten, Verwalten von PIN-Richtlinien für einwahlkonferenzen, Beitritt zur Konferenz verwalten und Ansagen lassen, ändern Sie den tastenzuordnungen für DTMF Befehle und einladen von Benutzern zu einwahlkonferenzen. 
  
Weitere Informationen zum Verwalten von Wähleinstellungen finden Sie unter [Erstellen oder Ändern von Wähleinstellungen in Skype für Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
Weitere Informationen zu PSTN-Verwendung finden Sie unter [Konfigurieren von VoIP-Richtlinien, PSTN-verwendungsdatensätzen und VoIP-Routen in Skype für Business 2015](../../deploy/deploy-enterprise-voice/voice-and-pstn.md).
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Verwalten von einwahlkonferenzen mithilfe von Skype Business Server-Systemsteuerung

So verwalten Sie Informationen über Einwahlkonferenzen:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenz**.
    
So verwalten Sie Informationen über Wähleinstellungen und die PSTN-Verwendung:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Verwalten von einwahlkonferenzen mithilfe von Skype für Business Server-Verwaltungsshell

Verwenden Sie zum Verwalten von einwahlkonferenzen mithilfe von Skype für Business Server-Verwaltungsshell die folgenden Cmdlets:
  
**Einwahl Konfigurationseinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Gibt Informationen zu den Konferenzverzeichnissen zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind. Konferenzverzeichnisse helfen den Benutzern von Einwahlkonferenzen beim Suchen nach Konferenzinformationen.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Ruft Informationen über wie Skype für Business Server reagiert, wenn Benutzer beitreten oder eine Konferenz einwählen verlassen.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Gibt Informationen über alle Zugriffsnummern für Einwahlkonferenzen zurück, die in Ihrer Organisation konfiguriert wurden.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Gibt die DTMF-Signaleinstellungen (Mehrfrequenzverfahren) zurück, die für Einwahlkonferenzen verwendet werden. Mit DTMF können Benutzer, die sich bei einer Konferenz einwählen, Konferenzeinstellungen mit der Telefontastatur steuern (z. B. eigene Person stummschalten bzw. Stummschaltung der eigenen Person aufheben oder Konferenz sperren bzw. entsperren).  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Gibt eine Liste der Sprachen, einschließlich Regions-/Minderheit Sprachen, für die Verwendung mit Skype für einwahlkonferenzen Business Server unterstützt. Diese Sprachen werden für die Übermittlung von Audionachrichten und Anweisungen für Benutzer verwendet, die mit einem Telefon an der Konferenz teilnehmen.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Gibt Informationen zu den in Ihrer Organisation verwendeten Sätzen mit Wähleinstellungen zurück.  <br/> |
|[GRANT-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Weist einem oder mehreren Benutzern oder Gruppen einen Wählplan zu.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Konferenzverzeichnisse importiert aus Microsoft Office Communications Server 2007 R2 zu Skype für Business Server. Dadurch wird die Interoperabilität zwischen Skype für Business Server und Office Communications Server 2007 R2 bereitstellen.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Verschiebt ein vorhandenes Konferenzverzeichnis aus einem Pool in einen anderen.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Erstellt ein neues Konferenzverzeichnis für die Verwendung in Ihrer Organisation.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Erstellt eine neue Zugriffsnummer für Einwahlkonferenzen.  <br/> |
|[Neue CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Erstellt eine neue Auflistung von einwahlkonferenzen Konfigurationseinstellungen. Diese Einstellungen bestimmen, wie Skype für Business Server reagiert, wenn Benutzer beitreten oder eine Konferenz einwählen verlassen. Insbesondere Informationen bezüglich unabhängig davon, ob Teilnehmer benötigt, um ihren Namen aufzeichnen müssen bei der Teilnahme an einer Konferenz, und wie werden zurückgegeben (oder ob) des Systems gibt bekannt, dass jemand hat sind oder diese verlassen des Anrufs.  <br/> |
|[Neue CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |Erstellt eine neue Auflistung von DTMF-Signaleinstellungen (Dual-Tone Multifrequency, Mehrfrequenzverfahren), die für Einwahlkonferenzen verwendet werden.  <br/> |
|[Neue CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Erstellt einen neuen Wählplan.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Entfernt ein vorhandenes Konferenzverzeichnis.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Entfernt eine vorhandene Zugriffsnummer für Einwahlkonferenzen.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Entfernt eine oder mehrere Auflistungen von Konfigurationseinstellungen für Einwahlkonferenzen. Diese Einstellungen bestimmen, wie Skype für Business Server reagiert, wenn Benutzer beitreten oder eine Konferenz einwählen verlassen.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Entfernt eine vorhandene Auflistung von DTMF-Signaleinstellungen (Dual Tone Multifrequency, Mehrfrequenzverfahren), die für Einwahlkonferenzen verwendet werden.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Ändert die Eigenschaftswerte einer vorhandenen Zugriffsnummer für Einwahlkonferenzen.  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Ändert Einstellungen, die bestimmen, wie Skype für Business Server reagiert, wenn Benutzer beitreten oder eine Konferenz einwählen verlassen.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Ändert die Einstellungen für die DTMF-Signalisierung (Dual-Tone Multifrequency, Mehrfrequenzverfahren), die für Einwahlkonferenzen verwendet werden.  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Ändert einen vorhandenen Wählplan.  <br/> |
   
**PIN-Richtlinieneinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Gibt Informationen zu den Client-PIN-Richtlinien zurück, die zur Verwendung in Ihrer Organisation konfiguriert sind. PIN-Authentifizierung ermöglicht Benutzern, Skype für Business Server zugreifen, indem Sie eine PIN anstatt einen Benutzernamen und ein Kennwort bereitstellen.  <br/> |
|[GRANT-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Weist einem Benutzer oder einer Benutzergruppe eine Client-PIN-Richtlinie zu.  <br/> |
|[Neue CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Erstellt eine neue Client-PIN-Richtlinie (PIN: persönliche Identifikationsnummer).  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Entfernt die angegebene PIN-Richtlinie (persönliche Identifikationsnummer).  <br/> |
|[Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Ändert eine oder mehrere vorhandene Clientrichtlinien für die persönliche Identifikationsnummer (PIN).  <br/> |
   

