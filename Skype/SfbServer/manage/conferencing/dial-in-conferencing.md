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
description: 'Zusammenfassung: Erfahren Sie, wie Sie Einwahlkonferenzen in Skype for Business Server verwalten.'
ms.openlocfilehash: 2674db010939f7b544ee296aea28739ecc7b806d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828155"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>Verwalten von Einwahlkonferenzen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Einwahlkonferenzen in Skype for Business Server verwalten.
  
In diesem Thema wird die Verwaltung von Einwahlkonferenzen beschrieben. Weitere Informationen zum Planen und Konfigurieren von Einwahlkonferenzen bei der Bereitstellung finden Sie unter "Planen von Einwahlkonferenzen [in Skype for Business Server"](../../plan-your-deployment/conferencing/dial-in-conferencing.md) und "Konfigurieren von Einwahlkonferenzen in Skype for Business [Server".](../../deploy/deploy-conferencing/dial-in-conferencing.md)
  
Sie können die folgenden Aufgaben zum Verwalten von Einwahlkonferenzen ausführen: Aktivieren oder Deaktivieren von Einwahlkonferenzen, Verwalten von Zugriffsnummern, Verwalten von PIN-Richtlinien für Einwahlkonferenzen, Verwalten von Ankündigungen für den Konferenzantritt und -verlassen, Ändern von Tastenzuordnungen für DTMF-Befehle und Willkommensbenutzer bei Einwahlkonferenzen. 
  
Weitere Informationen zum Verwalten von Wählplänen finden Sie unter Erstellen oder Ändern [eines Wählplans in Skype for Business Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)
  
Weitere Informationen zur PstN-Verwendung finden Sie unter ["Konfigurieren von Voicerichtlinien,](../../deploy/deploy-enterprise-voice/voice-and-pstn.md)PSTN-Verwendungsdatensätzen und Sprachrouten in Skype for Business".
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Verwalten von Einwahlkonferenzen mithilfe der Skype for Business Server-Systemsteuerung

So verwalten Sie Informationen zu Einwahlkonferenzen:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenz**.
    
So verwalten Sie Informationen zu Wählplänen und zur PSTN-Verwendung:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **"Sprachrouting".**
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Verwalten von Einwahlkonferenzen mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie die folgenden Cmdlets, um Einwahlkonferenzen mithilfe der Skype for Business Server-Verwaltungsshell zu verwalten:
  
**Konfigurationseinstellungen für die Einwahl**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Gibt Informationen zu den Konferenzverzeichnissen zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind. Konferenzverzeichnisse helfen den Benutzern von Einwahlkonferenzen beim Suchen nach Konferenzinformationen.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Ruft Informationen dazu ab, wie Skype for Business Server reagiert, wenn Benutzer einer Einwahlkonferenz beitreten oder diese verlassen.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Gibt Informationen zu allen Zugriffsnummern für Einwahlkonferenzen zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Gibt die für Einwahlkonferenzen verwendeten Einstellungen für die Mehrfrequenzsignalfunktion (Dual-Tone Multi-Frequency, DTMF) zurück. Mit DTMF können Benutzer, die sich in eine Konferenz einwählen, Konferenzeinstellungen (z. B. stummschalten und Stummschalten der eigenen Eigenen oder Sperren und Entsperren der Konferenz) über die Tastatur auf ihrem Telefon steuern.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Gibt eine Liste der Sprachen zurück, einschließlich Regional-/Minoritätssprachen, die für die Verwendung mit Skype for Business Server-Einwahlkonferenzen unterstützt werden. Diese Sprachen werden für die Übermittlung von Audionachrichten und Anweisungen für Benutzer verwendet, die mit einem Telefon an der Konferenz teilnehmen.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Gibt Informationen zu den in Ihrer Organisation verwendeten Wählplänen zurück.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Weist einem oder mehreren Benutzern oder Gruppen einen Wählplan zu.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importiert Konferenzverzeichnissen aus Microsoft Office Communications Server 2007 R2 in Skype for Business Server. Dadurch wird die Interoperabilität zwischen Skype for Business Server und Office Communications Server 2007 R2 ermöglicht.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Verschiebt ein vorhandenes Konferenzverzeichnis aus einem Pool in einen anderen.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Erstellt ein neues Konferenzverzeichnis für die Verwendung in Ihrer Organisation.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Erstellt eine neue Zugriffsnummer für Einwahlkonferenzen.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Erstellt eine neue Auflistung von Konfigurationseinstellungen für Einwahlkonferenzen. Diese Einstellungen bestimmen, wie Skype for Business Server reagiert, wenn Benutzer einer Einwahlkonferenz beitreten oder diese verlassen. Insbesondere werden Informationen darüber zurückgegeben, ob Teilnehmer ihren Namen aufzeichnen müssen, wenn sie einer Konferenz beitreten, und wie (oder ob) das System ansagt, dass jemand dem Anruf beigetreten ist oder diesen verlassen hat.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |Erstellt eine neue Auflistung von DTMF-Signaleinstellungen (Dual-Tone Multi-Frequency), die für Einwahlkonferenzen verwendet werden.  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Erstellt einen neuen Wählplan.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Entfernt ein vorhandenes Konferenzverzeichnis.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Entfernt eine vorhandene Zugriffsnummer für Einwahlkonferenzen.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Entfernt eine oder mehrere Auflistungen von Konfigurationseinstellungen für Einwahlkonferenzen. Diese Einstellungen bestimmen, wie Skype for Business Server reagiert, wenn Benutzer einer Einwahlkonferenz beitreten oder diese verlassen.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Entfernt eine vorhandene Auflistung von DtmF-Signaleinstellungen (Dual-Tone Multi-Frequency), die für Einwahlkonferenzen verwendet werden.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Ändert die Eigenschaftswerte einer vorhandenen Zugriffsnummer für Einwahlkonferenzen.  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Ändert Einstellungen, die bestimmen, wie Skype for Business Server reagiert, wenn Benutzer einer Einwahlkonferenz beitreten oder diese verlassen.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Ändert die Für Einwahlkonferenzen verwendeten DtmF-Signaleinstellungen (Dual-Tone Multifrequency).  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Ändert einen vorhandenen Wählplan.  <br/> |
   
**Einstellungen für die PIN-Richtlinie**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Gibt Informationen zu den Client-PIN-Richtlinien zurück, die zur Verwendung in Ihrer Organisation konfiguriert sind. Mit der PIN-Authentifizierung können Benutzer auf Skype for Business Server zugreifen, indem sie anstelle eines Benutzernamens und Kennworts eine PIN angeben.  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Weist einem Benutzer oder einer Benutzergruppe eine Clientrichtlinie für persönliche Identifikationsnummer (PIN) zu.  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Erstellt eine neue Client-PIN-Richtlinie (PIN: persönliche Identifikationsnummer).  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Entfernt die angegebene PIN-Richtlinie (persönliche Identifikationsnummer).  <br/> |
|[Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Ändert eine oder mehrere vorhandene Clientrichtlinien für persönliche Identifikationsnummer (PIN).  <br/> |
   

