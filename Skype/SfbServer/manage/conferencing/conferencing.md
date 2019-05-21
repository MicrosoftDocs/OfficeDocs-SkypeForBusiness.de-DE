---
title: Verwalten von Konferenzen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Konferenzen in Skype for Business Server verwalten.'
ms.openlocfilehash: 55fd2ff645e6e95199b2558ef494eea019b155bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280425"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>Verwalten von Konferenzen in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie Konferenzen in Skype for Business Server verwalten.
  
In diesem Themenbereich wird die Verwaltung von Konferenzen beschrieben. Weitere Informationen zum Planen und Bereitstellen von Konferenzen finden Sie unter [Planen von Konferenzen in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) und [Bereitstellen von Konferenzen in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
In Skype for Business Server verwalten Sie die Details von Konferenzen, indem Sie die Konfigurations-und Richtlinieneinstellungen wie folgt angeben. Beachten Sie, dass die Begriffe „Konferenz“ und „Besprechung“ manchmal synonym verwendet werden. Im Allgemeinen können Sie sich jedoch eine Besprechung als einen besonderen Fall einer Konferenz vorstellen.
  
- **Konferenzrichtlinieneinstellungen** umfassen eine breite Auswahl an Planungs- und Teilnahmeoptionen, von der Verwendung von IP-Audio und -Video in einer Besprechung bis hin zur Höchstzahl der möglichen Teilnehmer. Sie können die Konferenzrichtlinien verwenden, um die Sicherheit, die Bandbreite und die rechtlichen Aspekte von Besprechungen zu verwalten.
    
    Beachten Sie, dass Konferenzrichtlinien auf den Benutzer oder Standort angewendet werden und nicht auf eine konkrete Besprechung angewendet werden können. Daher kann die Besprechungseinladung für die Konferenz einige Wochen im Voraus erstellt werden, die Richtlinie für die restriktive Konferenz sollte jedoch unmittelbar vor Beginn der Konferenz auf das Skype for Business-Konto des Besprechungsorganisators angewendet werden. 
    
    Wenn ein dediziertes Konto für die Rolle des Besprechungsorganisators verwendet wird, kann die Konferenzrichtlinie diesem Konto zugewiesen bleiben. Wenn der Besprechungsorganisator ein allgemeines Skype for Business-Konto verwendet, muss die Richtlinie nach Abschluss der Konferenz entfernt werden.
    
- **Besprechungskonfigurationseinstellungen** legen fest, welche Arten von Besprechungen die Benutzer erstellen können. Zusätzlich steuern sie, wie (bzw. ob) anonyme Benutzer und Benutzer von Einwahlkonferenzen an diesen Besprechungen teilnehmen können. Beachten Sie, dass sich diese Einstellungen nur auf geplante Besprechungen auswirken. Besprechungskonfigurationen werden pro Pool, pro Standort oder global angewendet.
    
- Die **Konfigurationseinstellungen für Konferenzen** legen fest, wie groß die maximal zulässige Größe für Besprechungsinhalte und Handzettel sind. maximale Bandbreite für den Anwendungsfreigabe-Konferenzdienst; Speichergrenzwerte und Ablaufzeiten; die URLs für die internen und externen Downloads des unterstützten Clients; Zeiger auf interne und externe URLs, in denen Benutzer Konferenz Hilfen und-Ressourcen erhalten können; und die Ports, die für Anwendungsfreigabe, Client-Audio, Dateiübertragungen und Mediendatenverkehr verwendet werden.
    
    Diese Einstellungen ermöglichen es Ihnen, die eigentlichen Server selbst zu verwalten. Diese Einstellungen können nur über die Skype for Business Server-Verwaltungsshell eingestellt werden. 
    
- Mit den **Einwahlzugriffseinstellungen** können Sie bestimmen, ob und wie sich Nutzer über ein Telefon einwählen können. Sie bestimmen einige der Einwahlzugriffsinformationen, wie z. B. die Zugriffsnummer, über die Registerkarte „Konferenz“ der Systemsteuerung und einige Einwahlinformationen, wie z. B. Wählplan, VoIP-Richtlinie, Route und PSTN-Verwendung, über die Registerkarte „VoIP-Routing“ der Systemsteuerung.
    
- Mithilfe der **PIN-Richtlinieneinstellungen** können Sie die PIN benennen und festlegen, die Teilnehmer für den Einwahlzugriff verwenden müssen.
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>Verwalten von Konferenzen mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell

Sie können die meisten Konferenzrichtlinien und Konfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell verwalten. Einige Konfigurationseinstellungen stehen nur über die Skype for Business Server-Verwaltungsshell zur Verfügung.
  
- So verwalten Sie Konferenzrichtlinieneinstellungen:
    
  - Wählen Sie in der Systemsteuerung **Konferenzen | Konferenzrichtlinie** aus.
    
  - Suchen Sie in PowerShell nach den **-CsConferencingPolicy**-Cmdlets.
    
- So verwalten Sie Besprechungskonfigurationseinstellungen:
    
  - Wählen Sie in der Systemsteuerung **Konferenzen | Besprechungskonfiguration** aus.
    
  - Suchen Sie in der Skype for Business Server-Verwaltungsshell nach den **-CsMeetingConfiguration-** Cmdlets.
    
- So verwalten Sie Einstellungen für Einwahlzugriffsnummern:
    
  - Wählen Sie in der Systemsteuerung **Konferenzen | Einwahlzugriffsnummer** aus.
    
  - Suchen Sie in der Skype for Business Server-Verwaltungsshell nach den **-CsDialInConferencing-** Cmdlets.
    
- So verwalten Sie Einwahlzugriffsinformationen, wie z. B. Wählplan, VoIP-Richtlinie, Route und PSTN-Verwendung: 
    
  - Wählen Sie in der Systemsteuerung **Konferenzen | VoIP-Routing** aus.
    
  - Suchen Sie in der Skype for Business Server-Verwaltungsshell nach den Cmdlets **-CsDialPlan** und **-CsVoice** .
    
- So verwalten Sie PIN-Richtlinieneinstellungen:
    
  - Wählen Sie in der Systemsteuerung **Konferenzen | PIN-Richtlinie** aus.
    
  - Suchen Sie in der Skype for Business Server-Verwaltungsshell nach den **-CsPinPolicy-** Cmdlets.
    
- Zum Verwalten von Konferenz Konfigurationseinstellungen müssen Sie die Skype for Business Server-Verwaltungsshell verwenden. Suchen Sie nach **-CsConferencingConfiguration**-Cmdlets.
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Cmdlets für Skype for Business Server-Verwaltungsshell

Sie können die folgenden Cmdlets für die Verwaltung von Skype for Business Server-Verwaltungsshell verwenden, um Konferenzen zu verwalten: 
  
**Konferenzrichtlinieneinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Gibt Informationen zu den Konferenzrichtlinien zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind. Konferenzrichtlinien legen die in einer Besprechung zur Verfügung stehenden Funktionen fest, z. B. die Verfügbarkeit von IP-Audio und -Video für die Konferenz oder die zulässige Höchstanzahl von Teilnehmern einer Besprechung.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Weist einzelnen Benutzern eine Konferenzrichtlinie zu.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Erstellt eine neue Konferenzrichtlinie für die Verwendung in Ihrer Organisation.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Entfernt die angegebene Konferenzrichtlinie.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Ändert eine vorhandene Konferenzrichtlinie.  <br/> |
   
**Konfigurationseinstellungen für Besprechungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Gibt Informationen zu den Besprechungskonfigurationseinstellungen zurück, die derzeit in Ihrer Organisation verwendet werden. Konfigurationseinstellungen für Besprechungen legen fest, welche Arten von Besprechungen Benutzer erstellen können. Zusätzlich steuern sie, wie (bzw. ob) anonyme Benutzer und Benutzer von Einwahlkonferenzen an diesen Besprechungen teilnehmen können.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Erstellt eine neue Auflistung von Konfigurationseinstellungen für Besprechungen auf Standort- oder Dienstebene. Beachten Sie, dass sich diese Einstellungen nur auf geplante Besprechungen auswirken. Sie wirken sich nicht auf Ad-hoc-Besprechungen aus, die durch Klicken auf die Option "jetzt besprechen" in Skype for Business erstellt wurden.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Löscht eine vorhandene Auflistung von Konfigurationseinstellungen für Besprechungen.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Passt die derzeit in Ihrer Organisation verwendeten Besprechungskonfigurationseinstellungen an.  <br/> |
   
**Konferenzkonfigurationseinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Gibt Informationen zu den in Ihrer Organisation verwendeten Konferenzkonfigurationseinstellungen zurück. Mit Konferenzeinstellungen werden z. B. die maximal zulässige Größe für Konferenzinhalte und -handzettel, die Kulanzfrist für Inhalte (d. h. der Zeitraum, in dem Inhalte gespeichert werden, bevor sie gelöscht werden) und die URLs für interne und externe Downloads des unterstützten Clients festgelegt.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Erstellt eine neue Auflistung von Konferenzkonfigurationseinstellungen.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Entfernt die angegebene Auflistung von Konferenzkonfigurationseinstellungen.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Ändert eine vorhandene Auflistung von Konfigurationseinstellungen für Konferenzen.  <br/> |
   
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
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Verschiebt ein vorhandenes Konferenzverzeichnis aus einem Pool in einen anderen. Konferenzverzeichnisse helfen den Benutzern von Einwahlkonferenzen beim Suchen nach Konferenzinformationen.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Erstellt ein neues Konferenzverzeichnis für die Verwendung in Ihrer Organisation. Konferenzverzeichnisse helfen den Benutzern von Einwahlkonferenzen beim Suchen nach Konferenzinformationen.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Erstellt eine neue Zugriffsnummer für Einwahlkonferenzen.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Erstellt eine neue Sammlung von Konfigurationseinstellungen für Einwahlkonferenzen. Diese Einstellungen legen fest, wie Skype for Business Server antwortet, wenn Benutzer an einer Einwahlkonferenz teilnehmen oder diese hinterlassen. Insbesondere werden Informationen darüber zurückgegeben, ob die Teilnehmer ihren Namen bei der Teilnahme an einer Konferenz aufzeichnen müssen, und wie (oder wenn) das System ankündigt, dass jemand dem Anruf beigetreten ist oder ihn verlassen hat.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Erstellt eine neue Auflistung von DTMF-Signaleinstellungen (Dual-Tone Multifrequency, Mehrfrequenzverfahren), die für Einwahlkonferenzen verwendet werden.  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Erstellt einen neuen Wählplan.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Entfernt ein vorhandenes Konferenzverzeichnis. Konferenzverzeichnisse helfen den Benutzern von Einwahlkonferenzen beim Suchen nach Konferenzinformationen.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Entfernt eine vorhandene Zugriffsnummer für Einwahlkonferenzen.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Entfernt eine oder mehrere Auflistungen von Konfigurationseinstellungen für Einwahlkonferenzen. Diese Einstellungen legen fest, wie Skype for Business Server antwortet, wenn Benutzer an einer Einwahlkonferenz teilnehmen oder diese hinterlassen.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Entfernt eine vorhandene Auflistung von DTMF-Signaleinstellungen (Dual Tone Multifrequency, Mehrfrequenzverfahren), die für Einwahlkonferenzen verwendet werden.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Ändert die Eigenschaftswerte einer vorhandenen Zugriffsnummer für Einwahlkonferenzen. Bei Einwahlkonferenzen können Benutzer mit einem „normalen“ Telefon, einem Mobiltelefon oder einem anderen Gerät im Telefonfestnetz (Public Switched Telephone Network, PSTN) am Audioteil einer Konferenz teilnehmen.  <br/> |
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
   
**Andere Konferenzeinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |Deaktiviert einen Skype for Business Server-Besprechungsraum. Ein Besprechungsraum ist ein Konferenzmedium, das für Videokonferenzen und Szenarien der Zusammenarbeit in kleinen Konferenzräume entwickelt wurde. Wenn Sie ein Besprechungsraum Objekt deaktivieren, entfernen Sie alle von Skype for Business Server spezifischen Active Directory-Attribute, die dem Benutzerkonto zugeordnet sind, das den Besprechungsraum repräsentiert. Das Active Directory-Benutzerkonto wird allerdings nicht gelöscht.  <br/> |
|[Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |Ermöglicht einen Skype for Business Server-Besprechungsraum. Zum Aktivieren eines Besprechungsraums müssen Sie zunächst ein Active Directory-Benutzerkonto erstellen, das das System darstellt. Hinweis: Obwohl Besprechungsraumobjekte auf Benutzerkonten basieren, werden diese Objekte beim Ausführen des Cmdlets Get-CsUser nicht angezeigt.  <br/> |
|[Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |Gibt Informationen zu dem in Ihrer Organisation verwendeten Konferenzhaftungsausschluss zurück. Der Konferenzhaftungsausschluss ist eine Meldung, die Benutzern angezeigt wird, die der Konferenz über einen Link beitreten (z. B. Benutzer, die einen Konferenzlink in einen Browser wie Windows Internet Explorer einfügen).  <br/> |
|[Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |Gibt Informationen zu allen Skype for Business Server-Besprechungsräumen zurück, die für die Verwendung in der Organisation konfiguriert sind.  <br/> |
|[Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |Verschiebt ein Skype for Business Server-Besprechungsraum Objekt von einem registrierungsstellenpool in einen anderen.  <br/> |
|[Remove-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |Löscht den Text aus dem Header und aus dem Hauptteil des in Ihrer Organisation verwendeten Konferenzhaftungsausschlusses. Der Konferenzhaftungsausschluss ist eine Meldung, die Benutzern angezeigt wird, die der Konferenz über einen Link beitreten (z. B. Benutzer, die einen Konferenzlink in einen Browser wie Windows Internet Explorer einfügen).  <br/> |
|[Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |Ändert die Eigenschaftswerte eines vorhandenen Skype for Business Server-Besprechungsraums.  <br/> |
   
**Testeinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |Testet, ob ein Benutzerpaar an einer Konferenz zur Anwendungsfreigabe teilnehmen kann.  <br/> |
|[Test-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |Hiermit wird getestet, ob ein Benutzer eine Verbindung mit seinem Audiokonferenzanbieter herstellen kann. Bei einem Audiokonferenzanbieter handelt es sich um ein Drittanbieterunternehmen, das Konferenzdienste für Organisationen bereitstellt. Audiokonferenzanbieter bieten Benutzern u. a. die Möglichkeit, von außerhalb eines Standorts und ohne Verbindung mit dem Unternehmensnetzwerk oder dem Internet am Audioteil einer Konferenz oder Besprechung teilzunehmen.  <br/> |
|[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |Testet, ob ein Benutzerpaar an einer Audio-/Videokonferenz teilnehmen kann.  <br/> |
|[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |Überprüft, ob ein Benutzer Paar an einer Skype for Business Server-Webkonferenz teilnehmen kann, die Aktivitäten wie das Freigeben oder Anzeigen von PowerPoint-Folien, Whiteboards oder Umfragen umfasst. Das Cmdlet überprüft auch, ob der Skype for Business Server-Webkonferenzdienst Office Web Apps Server ermitteln kann und dass ein Client eine PowerPoint-Datei hochladen kann, die von Office Web Apps Server übertragen wird.  <br/> |
|[Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |Überprüft, ob ein Benutzer an einer Einwahlkonferenzsitzung teilnehmen kann.  <br/> |
|[Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |Testet einen Wählplan (ehemals als Standortprofil bezeichnet) für eine Telefonnummer und gibt die Normalisierungsregel, die auf diese Nummer angewendet wird, sowie die übersetzte Nummer nach dem Anwenden der Normalisierungsregel zurück.  <br/> |
|[Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |Testet die Möglichkeit von drei Benutzern, an einer Skype for Business Server-Mobilitätsdienst Konferenz teilzunehmen. Mit dem Mobilitätsdienst können Nutzer von Mobiltelefonen wie iPhones und Windows phones beispielsweise Exchange-Sofortnachrichten und Anwesenheitsinformationen austauschen. Speichern und Abrufen von Voicemail intern und nicht mit Ihrem WLAN-Anbieter; und nutzen Sie die Vorteile von Skype for Business Server-Funktionen wie Anruf über Arbeit und Einwahlkonferenzen.  <br/> **Hinweis:** Clients, die MCX verwenden, werden in Skype for Business Server 2019 nicht unterstützt.|
|[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |Testet, ob zwei Benutzer mithilfe der Unified Communications Web-API (UCWA) eine Onlinekonferenz planen, dieser beitreten und die Konferenz dann durchführen können.  <br/> |
|[Debug-CsDataConference](https://docs.microsoft.com/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |Gibt Diagnoseinformationen für die Datenkonferenz Funktionen zurück, die in Skype for Business Server enthalten sind.  <br/> |
   

