---
title: Verwalten von Konferenzen in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: 'Zusammenfassung: Erfahren Sie, wie Sie Konferenzen in Skype for Business Server verwalten.'
ms.openlocfilehash: ef1afdecaec5ae237020b1681d95b556a37e2ab8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751774"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>Verwalten von Konferenzen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Konferenzen in Skype for Business Server verwalten.
  
In diesem Thema wird beschrieben, wie Sie Konferenzen verwalten. Weitere Informationen zum Planen und Bereitstellen von Konferenzen finden Sie unter [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and Deploy [conferencing in Skype for Business Server.](../../deploy/deploy-conferencing/deploy-conferencing.md)
  
In Skype for Business Server verwalten Sie die Details von Konferenzen, indem Sie die Konfigurations- und Richtlinieneinstellungen wie folgt angeben. Beachten Sie, dass die Begriffe "Konferenzen" und "Besprechung" manchmal synonym verwendet werden. Aber im Allgemeinen können Sie sich eine Besprechung als eine bestimmte Instanz von Konferenzen vorstellen.
  
- **Die Konferenzrichtlinieneinstellungen** umfassen eine Vielzahl von Planungs- und Teilnahmeoptionen, von der Frage, ob eine Besprechung IP-Audio und -Video enthalten kann, bis hin zur maximalen Anzahl von Personen, die teilnehmen können. Sie können Konferenzrichtlinien verwenden, um Sicherheit, Bandbreite und rechtliche Aspekte von Besprechungen zu verwalten.
    
    Beachten Sie, dass Konferenzrichtlinien auf den Benutzer oder Standort angewendet werden und nicht auf eine bestimmte Besprechung angewendet werden können. Daher kann die Besprechungseinladung für die Konferenz einige Wochen im Voraus erstellt werden, aber die restriktive Konferenzrichtlinie sollte auf das Skype for Business Konto des Besprechungsorganisators unmittelbar vor Beginn der Konferenz angewendet werden. 
    
    Wenn ein dediziertes Konto für die Rolle "Besprechungsorganisator" verwendet wird, kann die Konferenzrichtlinie diesem Konto zugewiesen bleiben. Wenn der Besprechungsorganisator ein allgemeines Skype for Business Konto verwendet, muss die Richtlinie nach Abschluss der Konferenz entfernt werden.
    
- **Besprechungskonfigurationseinstellungen** bestimmen die Art der Besprechungen, die Benutzer erstellen können, und steuern, wie (oder auch wenn) anonyme Benutzer und Benutzer von Einwahlkonferenzen an diesen Besprechungen teilnehmen können. Beachten Sie, dass sich diese Einstellungen nur auf geplante Besprechungen auswirken. Besprechungskonfigurationen werden pro Pool, pro Standort oder global angewendet.
    
- **Die Konferenzkonfigurationseinstellungen** bestimmen z. B. die maximal zulässige Größe für Besprechungsinhalte und Handzettel; maximale Bandbreite für den Konferenzdienst für anwendungsfreigabe; Speicherlimits und Ablaufzeiten; die URLs für die internen und externen Downloads des unterstützten Clients; Zeiger auf interne und externe URLs, in denen Benutzer Hilfe und Ressourcen für Konferenzen erhalten können; und die Ports für Anwendungsfreigabe, Clientaudio, Dateiübertragungen und Mediendatenverkehr.
    
    Mit diesen Einstellungen können Sie die eigentlichen Server selbst verwalten. Diese Einstellungen können nur mithilfe Skype for Business Server Verwaltungsshell festgelegt werden. 
    
- Mit den Zugriffseinstellungen für **die Einwahl** können Sie Informationen darüber definieren, ob und wie sich Benutzer über ein Telefon einwählen. Auf der Registerkarte "VoIP-Routing" der Systemsteuerung geben Sie auf der Registerkarte "Systemsteuerungskonferenzen" einige Informationen zum Einwahlzugriff an, z. B. Die Zugriffsnummer und einige Einwahlinformationen wie Wählplan, VoIP-Richtlinie, Route und PSTN-Verwendung.
    
- Mithilfe von **PIN-Richtlinieneinstellungen** können Sie die PIN benennen und definieren, die Teilnehmer für den Einwahlzugriff verwenden.
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>Verwalten von Konferenzen mithilfe Skype for Business Server Systemsteuerung oder mithilfe Skype for Business Server Verwaltungsshell

Sie können die meisten Konferenzrichtlinien und Konfigurationseinstellungen mithilfe Skype for Business Server Systemsteuerung oder mithilfe Skype for Business Server Verwaltungsshell verwalten. Einige Konfigurationseinstellungen sind nur mithilfe Skype for Business Server Verwaltungsshell verfügbar.
  
- So verwalten Sie Konferenzrichtlinieneinstellungen:
    
  - Wählen Sie in der Systemsteuerung **"Konferenzen | Konferenzrichtlinie**.
    
  - Suchen Sie in PowerShell nach den Cmdlets **"-CsConferencingPolicy".**
    
- So verwalten Sie Besprechungskonfigurationseinstellungen:
    
  - Wählen Sie in der Systemsteuerung **"Konferenzen | Besprechungskonfiguration**.
    
  - Suchen Sie in Skype for Business Server Verwaltungsshell nach den **-CsMeetingConfiguration-Cmdlets.**
    
- So verwalten Sie Die Einstellungen für die Zugriffsnummer für die Einwahl:
    
  - Wählen Sie in der Systemsteuerung **"Konferenzen | Zugriffsnummer für Einwahl.**
    
  - Suchen Sie in Skype for Business Server Verwaltungsshell nach den **-CsDialInConferencing-Cmdlets.**
    
- So verwalten Sie Einwahlzugriffsinformationen wie Wählplan, VoIP-Richtlinie, Route und PSTN-Verwendung: 
    
  - Wählen Sie in der Systemsteuerung **"Konferenzen | VoIP-Routing**.
    
  - Suchen Sie in Skype for Business Server Verwaltungsshell nach den Cmdlets **"-CsDialPlan"** und **"-CsVoice".**
    
- So verwalten Sie PIN-Richtlinieneinstellungen:
    
  - Wählen Sie in der Systemsteuerung **"Konferenzen | PIN-Richtlinie**.
    
  - Suchen Sie in Skype for Business Server Verwaltungsshell nach den Cmdlets **"-CsPinPolicy".**
    
- Zum Verwalten von Konferenzkonfigurationseinstellungen müssen Sie die Skype for Business Server-Verwaltungsshell verwenden. Suchen Sie nach **-CsConferencingConfiguration-Cmdlets.**
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Skype for Business Server Cmdlets der Verwaltungsshell

Sie können die folgenden Cmdlets Skype for Business Server Verwaltungsshell verwenden, um Konferenzen zu verwalten: 
  
**Konferenzrichtlinieneinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Gibt Informationen zu den Konferenzrichtlinien zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind. Konferenzrichtlinien legen die in einer Besprechung zur Verfügung stehenden Funktionen fest, z. B. die Verfügbarkeit von IP-Audio und -Video für die Konferenz oder die zulässige Höchstanzahl von Teilnehmern einer Besprechung.  <br/> |
|[Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Weist eine Konferenzrichtlinie auf Benutzerebene zu.  <br/> |
|[New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Erstellt eine neue Konferenzrichtlinie für die Verwendung in Ihrer Organisation.  <br/> |
|[Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Entfernt die angegebene Konferenzrichtlinie.  <br/> |
|[Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Ändert eine vorhandene Konferenzrichtlinie.  <br/> |
   
**Konfigurationseinstellungen für Besprechungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Gibt Informationen zu den derzeit in Ihrer Organisation verwendeten Besprechungskonfigurationseinstellungen zurück. Besprechungskonfigurationseinstellungen bestimmen die Art der Besprechungen, die Benutzer erstellen können, und steuern, wie (oder auch wenn) anonyme Benutzer und Benutzer von Einwahlkonferenzen an diesen Besprechungen teilnehmen können.  <br/> |
|[New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Erstellt eine neue Auflistung von Besprechungskonfigurationseinstellungen auf Standort- oder Dienstebene. Beachten Sie, dass sich diese Einstellungen nur auf geplante Besprechungen auswirken. Sie wirken sich nicht auf Ad-hoc-Besprechungen aus, die durch Klicken auf die Option "Jetzt besprechen" in Skype for Business erstellt wurden.  <br/> |
|[Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Löscht eine vorhandene Sammlung von Besprechungskonfigurationseinstellungen.  <br/> |
|[Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Ändert die Besprechungskonfigurationseinstellungen, die derzeit in Ihrer Organisation verwendet werden.  <br/> |
   
**Konfigurationseinstellungen für Konferenzen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Gibt Informationen zu den in Ihrer Organisation verwendeten Konferenzkonfigurationseinstellungen zurück. Mit Konferenzeinstellungen werden z. B. die maximal zulässige Größe für Konferenzinhalte und -handzettel, die Kulanzfrist für Inhalte (d. h. der Zeitraum, in dem Inhalte gespeichert werden, bevor sie gelöscht werden) und die URLs für interne und externe Downloads des unterstützten Clients festgelegt.  <br/> |
|[New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Erstellt eine neue Auflistung von Konferenzkonfigurationseinstellungen.  <br/> |
|[Remove-CsConferencingConfiguration](/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Entfernt die angegebene Auflistung von Konferenzkonfigurationseinstellungen.  <br/> |
|[Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Ändert eine vorhandene Auflistung von Konfigurationseinstellungen für Konferenzen.  <br/> |
   
**Konfigurationseinstellungen für die Einwahl**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsConferenceDirectory](/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Gibt Informationen zu den Konferenzverzeichnissen zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind. Konferenzverzeichnisse helfen den Benutzern von Einwahlkonferenzen beim Suchen nach Konferenzinformationen.  <br/> |
|[Get-CsDialInConferencingConfiguration](/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Ruft Informationen dazu ab, wie Skype for Business Server reagiert, wenn Benutzer einer Einwahlkonferenz beitreten oder diese verlassen.  <br/> |
|[Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Gibt Informationen zu allen Zugriffsnummern für Einwahlkonferenzen zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Gibt die DTMF-Signaleinstellungen (Dual-Tone Multifrequency) zurück, die für Einwahlkonferenzen verwendet werden. Mit DTMF können Benutzer, die sich in eine Konferenz einwählen, Konferenzeinstellungen steuern (z. B. das Stummschalten und Aufheben der Stummschaltung selbst oder das Sperren und Entsperren der Konferenz) mithilfe der Tastatur auf ihrem Telefon.  <br/> |
|[Get-CsDialInConferencingLanguageList](/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Gibt eine Liste der Sprachen zurück, einschließlich Regional-/Regionalsprachen, die für die Verwendung mit Skype for Business Server Einwahlkonferenzen unterstützt werden. Diese Sprachen werden für die Übermittlung von Audionachrichten und Anweisungen für Benutzer verwendet, die mit einem Telefon an der Konferenz teilnehmen.  <br/> |
|[Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Gibt Informationen zu den in Ihrer Organisation verwendeten Wählplänen zurück.  <br/> |
|[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Weist einem oder mehreren Benutzern oder Gruppen einen Wählplan zu.  <br/> |
|[Import-CsLegacyConferenceDirectory](/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importiert Konferenzverzeichnisse aus Microsoft Office Communications Server 2007 R2 in Skype for Business Server. Dies trägt zur Interoperabilität zwischen Skype for Business Server und Office Communications Server 2007 R2 bei.  <br/> |
|[Move-CsConferenceDirectory](/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Verschiebt ein vorhandenes Konferenzverzeichnis aus einem Pool in einen anderen. Konferenzverzeichnisse helfen den Benutzern von Einwahlkonferenzen beim Suchen nach Konferenzinformationen.  <br/> |
|[New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Erstellt ein neues Konferenzverzeichnis für die Verwendung in Ihrer Organisation. Konferenzverzeichnisse helfen den Benutzern von Einwahlkonferenzen beim Suchen nach Konferenzinformationen.  <br/> |
|[New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Erstellt eine neue Zugriffsnummer für Einwahlkonferenzen.  <br/> |
|[New-CsDialInConferencingConfiguration](/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Erstellt eine neue Auflistung von Konfigurationseinstellungen für Einwahlkonferenzen. Diese Einstellungen bestimmen, wie Skype for Business Server reagiert, wenn Benutzer einer Einwahlkonferenz beitreten oder diese verlassen. Insbesondere werden Informationen darüber zurückgegeben, ob Teilnehmer ihren Namen bei der Teilnahme an einer Konferenz aufzeichnen müssen und wie (oder ob) das System angibt, dass jemand dem Anruf beigetreten ist oder diesen verlassen hat.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Erstellt eine neue Sammlung von DTMF-Signaleinstellungen (Dual-Tone Multifrequency), die für Einwahlkonferenzen verwendet werden.  <br/> |
|[New-CsDialPlan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Erstellt einen neuen Wählplan.  <br/> |
|[Remove-CsConferenceDirectory](/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Entfernt ein vorhandenes Konferenzverzeichnis. Konferenzverzeichnisse helfen den Benutzern von Einwahlkonferenzen beim Suchen nach Konferenzinformationen.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Entfernt eine vorhandene Zugriffsnummer für Einwahlkonferenzen.  <br/> |
|[Remove-CsDialInConferencingConfiguration](/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Entfernt eine oder mehrere Auflistungen von Konfigurationseinstellungen für Einwahlkonferenzen. Diese Einstellungen bestimmen, wie Skype for Business Server reagiert, wenn Benutzer einer Einwahlkonferenz beitreten oder diese verlassen.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Entfernt eine vorhandene Sammlung von DTMF-Signaleinstellungen (Dual-Tone Multi-Frequency), die für Einwahlkonferenzen verwendet werden.  <br/> |
|[Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Ändert die Eigenschaftswerte einer vorhandenen Zugriffsnummer für Einwahlkonferenzen. Bei Einwahlkonferenzen können Benutzer mit einem "normalen" Telefon, einem Mobiltelefon oder einem anderen Gerät im Telefonfestnetz (Public Switched Telephone Network, PSTN) am Audioteil einer Konferenz teilnehmen.  <br/> |
|[Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Ändert Einstellungen, die bestimmen, wie Skype for Business Server reagiert, wenn Benutzer einer Einwahlkonferenz beitreten oder diese verlassen.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Ändert die DTMF-Signaleinstellungen (Dual-Tone Multifrequency), die für Einwahlkonferenzen verwendet werden.  <br/> |
|[Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Ändert einen vorhandenen Wählplan.  <br/> |
   
**PIN-Richtlinieneinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Gibt Informationen zu den Client-PIN-Richtlinien zurück, die zur Verwendung in Ihrer Organisation konfiguriert sind. Die PIN-Authentifizierung ermöglicht Benutzern den Zugriff auf Skype for Business Server, indem eine PIN anstelle eines Benutzernamens und Kennworts bereitgestellt wird.  <br/> |
|[Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Weist einem Benutzer oder einer Benutzergruppe eine PIN-Richtlinie (Persönliche Identifikationsnummer) des Clients zu.  <br/> |
|[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Erstellt eine neue Client-PIN-Richtlinie (PIN: persönliche Identifikationsnummer).  <br/> |
|[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Entfernt die angegebene PIN-Richtlinie (persönliche Identifikationsnummer).  <br/> |
|[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Ändert eine oder mehrere vorhandene PIN-Richtlinien (Client Personal Identification Number).  <br/> |
   
**Andere Konferenzeinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Disable-CsMeetingRoom](/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |Deaktiviert einen Skype for Business Server Besprechungsraum. Ein Besprechungsraum ist ein Konferenzmedium, das für Videokonferenzen und Szenarien der Zusammenarbeit in kleinen Konferenzräume entwickelt wurde. Wenn Sie ein Besprechungsraumobjekt deaktivieren, entfernen Sie alle Skype for Business Server spezifischen Active Directory-Attribute, die dem Benutzerkonto zugewiesen sind, das den Besprechungsraum darstellt. Das Active Directory-Benutzerkonto wird allerdings nicht gelöscht.  <br/> |
|[Enable-CsMeetingRoom](/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |Aktiviert einen Skype for Business Server Besprechungsraum. Um einen Besprechungsraum zu aktivieren, müssen Sie zunächst ein Active Directory-Benutzerkonto erstellen, das dieses System darstellt. Beachten Sie, dass Besprechungsraumobjekte zwar auf Benutzerkonten basieren, diese Objekte jedoch nicht angezeigt werden, wenn Sie das Cmdlet Get-CsUser ausführen.  <br/> |
|[Get-CsConferenceDisclaimer](/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |Gibt Informationen zu dem in Ihrer Organisation verwendeten Konferenzhaftungsausschluss zurück. Der Konferenzhaftungssausschluss ist eine Meldung, die Benutzern angezeigt wird, die der Konferenz über einen Link beitreten (z. B. Benutzer, die einen Konferenzlink in einen Browser wie Windows Internet Explorer einfügen).  <br/> |
|[Get-CsMeetingRoom](/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |Gibt Informationen zu allen Skype for Business Server Besprechungsräumen zurück, die für die Verwendung in der Organisation konfiguriert sind.  <br/> |
|[Move-CsMeetingRoom](/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |Verschiebt ein Skype for Business Server Besprechungsraumobjekt von einem Registrierungsstellenpool in einen anderen.  <br/> |
|[Remove-CsConferenceDisclaimer](/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |Löscht den Text aus dem Header und aus dem Hauptteil des in Ihrer Organisation verwendeten Konferenzhaftungsausschlusses. Der Konferenzhaftungssausschluss ist eine Meldung, die Benutzern angezeigt wird, die der Konferenz über einen Link beitreten (z. B. Benutzer, die einen Konferenzlink in einen Browser wie Windows Internet Explorer einfügen).  <br/> |
|[Set-CsMeetingRoom](/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |Ändert die Eigenschaftswerte eines vorhandenen Skype for Business Server Besprechungsraums.  <br/> |
   
**Testeinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Test-CsASConference](/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |Testet, ob ein Benutzerpaar an einer Konferenz zur Anwendungsfreigabe teilnehmen kann.  <br/> |
|[Test-CsAudioConferencingProvider](/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |Hiermit wird getestet, ob ein Benutzer eine Verbindung mit seinem Audiokonferenzanbieter herstellen kann. Bei einem Audiokonferenzanbieter handelt es sich um ein Drittanbieterunternehmen, das Konferenzdienste für Organisationen bereitstellt. Audiokonferenzanbieter bieten Benutzern u. a. die Möglichkeit, von außerhalb eines Standorts und ohne Verbindung mit dem Unternehmensnetzwerk oder dem Internet am Audioteil einer Konferenz oder Besprechung teilzunehmen.  <br/> |
|[Test-CsAVConference](/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |Testet, ob ein Benutzerpaar an einer Audio-/Videokonferenz teilnehmen kann.  <br/> |
|[Test-CsDataConference](/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |Überprüft, ob ein Benutzerpaar an einer Skype for Business Server Webkonferenz teilnehmen kann, die Aktivitäten wie das Freigeben oder Anzeigen PowerPoint Folien, Whiteboards oder Umfragen umfasst. Das Cmdlet überprüft außerdem, ob der Skype for Business Server Webkonferenzdienst Office Web Apps-Server ermitteln kann und ob ein Client eine PowerPoint-Datei zur Übertragung durch Office Web Apps Server hochladen kann.  <br/> |
|[Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |Überprüft, ob ein Benutzer an einer Einwahlkonferenzsitzung teilnehmen kann.  <br/> |
|[Test-CsDialPlan](/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |Testet einen Wählplan (ehemals als Standortprofil bezeichnet) für eine Telefonnummer und gibt die Normalisierungsregel, die auf diese Nummer angewendet wird, sowie die übersetzte Nummer nach dem Anwenden der Normalisierungsregel zurück.  <br/> |
|[Test-CsMcxConference](/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |Testet die Fähigkeit von drei Benutzern, an einer Skype for Business Server Mobility Service-Konferenz teilzunehmen. Der Mobilitätsdienst ermöglicht Es Benutzern von Mobiltelefonen wie iPhones und Windows Telefonen, Beispielsweise Chatnachrichten und Anwesenheitsinformationen auszutauschen. Internes Speichern und Abrufen von Voicemail anstelle des Drahtlosanbieters; und nutzen Sie Skype for Business Server Funktionen wie "Anruf über Arbeit" und Ausgehende Konferenzen.  <br/> **Hinweis:** Clients, die MCX verwenden, werden in Skype for Business Server 2019 nicht unterstützt.|
|[Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |Testet die Fähigkeit eines Benutzerpaars, eine Onlinekonferenz mithilfe der Unified Communications Web API (UCWA) zu planen, daran teilzunehmen und dann eine Onlinekonferenz durchzuführen.  <br/> |
|[Debug-CsDataConference](/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |Gibt Diagnoseinformationen für die in Skype for Business Server enthaltenen Datenkonferenzfunktionen zurück.  <br/> |
