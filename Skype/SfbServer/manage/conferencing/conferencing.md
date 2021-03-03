---
title: Verwalten von Konferenzen in Skype for Business Server
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
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: 'Zusammenfassung: Erfahren Sie, wie Sie Konferenzen in Skype for Business Server verwalten.'
ms.openlocfilehash: b1df4a339d7764c86ba76804dc67d1e1f11fc397
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810215"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>Verwalten von Konferenzen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Konferenzen in Skype for Business Server verwalten.
  
In diesem Thema wird die Verwaltung von Konferenzen beschrieben. Weitere Informationen zum Planen und Bereitstellen von Konferenzen finden Sie unter "Planen von Konferenzen [in Skype for Business Server"](../../plan-your-deployment/conferencing/conferencing.md) und "Bereitstellen von Konferenzen in Skype for Business [Server".](../../deploy/deploy-conferencing/deploy-conferencing.md)
  
In Skype for Business Server verwalten Sie die Details von Konferenzen, indem Sie die Konfigurations- und Richtlinieneinstellungen wie folgt angeben. Beachten Sie, dass die Begriffe Konferenz und Besprechung manchmal synonym verwendet werden. Aber im Allgemeinen können Sie sich eine Besprechung als eine bestimmte Instanz von Konferenzen einsenden.
  
- **Die Konferenzrichtlinieneinstellungen** umfassen eine Vielzahl von Planungs- und Teilnahmeoptionen, von der Frage, ob eine Besprechung IP-Audio- und -Videodaten enthalten kann, bis hin zur maximalen Anzahl von Personen, die teilnehmen können. Sie können Konferenzrichtlinien verwenden, um Sicherheits-, Bandbreiten- und rechtliche Aspekte von Besprechungen zu verwalten.
    
    Beachten Sie, dass Konferenzrichtlinien auf den Benutzer oder Standort angewendet werden und nicht auf eine bestimmte Besprechung angewendet werden können. Daher kann die Besprechungseinladung für die Konferenz einige Wochen im Voraus erstellt werden, aber die restriktive Konferenzrichtlinie sollte auf das Skype for Business-Konto des Besprechungsorganisators angewendet werden, kurz bevor die Konferenz beginnt. 
    
    Wenn ein dediziertes Konto für die Rolle "Besprechungsorganisator" verwendet wird, kann die Konferenzrichtlinie diesem Konto zugewiesen bleiben. Wenn der Besprechungsorganisator ein allgemeines Skype for Business-Konto verwendet, muss die Richtlinie nach Abschluss der Konferenz entfernt werden.
    
- **Besprechungskonfigurationseinstellungen** bestimmen die Art von Besprechungen, die Benutzer erstellen können, und steuern zusätzlich, wie (oder auch ob) anonyme Benutzer und Benutzer von Einwahlkonferenzen an diesen Besprechungen teilnehmen können. Beachten Sie, dass sich diese Einstellungen nur auf geplante Besprechungen auswirken. Besprechungskonfigurationen werden pro Pool, Standort oder global angewendet.
    
- **Konferenzkonfigurationseinstellungen** bestimmen z. B. die maximal zulässige Größe für Besprechungsinhalte und Handzettel. maximale Bandbreite für den Konferenzdienst für anwendungsfreigaben; Speichergrenzwerte und Ablaufzeiträume; die URLs für die internen und externen Downloads des unterstützten Clients; zeigers to internal and external URLs where users can obtain conferencing help and resources; und die Ports, die für anwendungsfreigabe, Clientaudio, Dateiübertragungen und Mediendatenverkehr verwendet werden.
    
    Mit diesen Einstellungen können Sie die eigentlichen Server selbst verwalten. Diese Einstellungen können nur mithilfe der Skype for Business Server-Verwaltungsshell festgelegt werden. 
    
- **Mit den Zugriffseinstellungen für die** Einwahl können Sie Informationen darüber definieren, ob und wie sich Benutzer über ein Telefon einwählen. Über die Registerkarte "Systemsteuerungs-Voicerouting" geben Sie einige der Zugriffsinformationen für die Einwahl an, z. B. die Zugriffsnummer, und einige Einwahlinformationen , z. B. Wählplan, Sprachrichtlinie, Route und PSTN-Verwendung.
    
- **Mit den Einstellungen für** die PIN-Richtlinie können Sie die PIN benennen und definieren, die Teilnehmer für den Einwahlzugriff verwenden.
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>Verwalten von Konferenzen mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell

Sie können die meisten Konferenzrichtlinien und Konfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell verwalten. Einige Konfigurationseinstellungen sind nur mithilfe der Skype for Business Server-Verwaltungsshell verfügbar.
  
- So verwalten Sie Konferenzrichtlinieneinstellungen:
    
  - Wählen Sie in der Systemsteuerung **"Konferenzen" | Konferenzrichtlinie**.
    
  - Suchen Sie in PowerShell nach den **Cmdlets "-CsConferencingPolicy".**
    
- So verwalten Sie Besprechungskonfigurationseinstellungen:
    
  - Wählen Sie in der Systemsteuerung **"Konferenzen" | Besprechungskonfiguration**.
    
  - Suchen Sie in der Skype for Business Server-Verwaltungsshell nach den **Cmdlets "-CsMeetingConfiguration".**
    
- So verwalten Sie Die Einstellungen für Die Zugriffsnummer für die Einwahl:
    
  - Wählen Sie in der Systemsteuerung **"Konferenzen" | Zugriffsnummer für die Einwahl.**
    
  - Suchen Sie in der Skype for Business Server-Verwaltungsshell nach den **Cmdlets "-CsDialInConferencing".**
    
- So verwalten Sie Einwahlzugriffsinformationen wie Wählplan, Sprachrichtlinie, Route und PSTN-Verwendung: 
    
  - Wählen Sie in der Systemsteuerung **"Konferenzen" | Sprachrouting**.
    
  - Suchen Sie in der Skype for Business Server-Verwaltungsshell nach den Cmdlets **"-CsDialPlan"** und **"-CsVoice".**
    
- So verwalten Sie PIN-Richtlinieneinstellungen:
    
  - Wählen Sie in der Systemsteuerung **"Konferenzen" | PIN-Richtlinie**.
    
  - Suchen Sie in der Skype for Business Server-Verwaltungsshell nach den **Cmdlets "-CsPinPolicy".**
    
- Zum Verwalten von Konferenzkonfigurationseinstellungen müssen Sie die Skype for Business Server-Verwaltungsshell verwenden. Suchen Sie **nach -CsConferencingConfiguration-Cmdlets.**
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Cmdlets für die Skype for Business Server-Verwaltungsshell

Sie können die folgenden Skype for Business Server-Verwaltungsshell-Cmdlets zum Verwalten von Konferenzen verwenden: 
  
**Konferenzrichtlinieneinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Gibt Informationen zu den Konferenzrichtlinien zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind. Konferenzrichtlinien legen die in einer Besprechung zur Verfügung stehenden Funktionen fest, z. B. die Verfügbarkeit von IP-Audio und -Video für die Konferenz oder die zulässige Höchstanzahl von Teilnehmern einer Besprechung.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Weist eine Konferenzrichtlinie auf Benutzerbereich zu.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Erstellt eine neue Konferenzrichtlinie für die Verwendung in Ihrer Organisation.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Entfernt die angegebene Konferenzrichtlinie.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Ändert eine vorhandene Konferenzrichtlinie.  <br/> |
   
**Konfigurationseinstellungen für Besprechungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Gibt Informationen zu den derzeit in Ihrer Organisation verwendeten Besprechungskonfigurationseinstellungen zurück. Mithilfe von Besprechungskonfigurationseinstellungen können Sie festlegen, welche Art von Besprechungen Benutzer erstellen können, und steuern, wie (oder auch ob) anonyme Benutzer und Benutzer von Einwahlkonferenzen an diesen Besprechungen teilnehmen können.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Erstellt eine neue Auflistung von Besprechungskonfigurationseinstellungen auf Standort- oder Dienstseite. Beachten Sie, dass sich diese Einstellungen nur auf geplante Besprechungen auswirken. sie wirken sich nicht auf Ad-hoc-Besprechungen aus, die durch Klicken auf die Option "Sofortbesprechungen" in Skype for Business erstellt werden.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Löscht eine vorhandene Auflistung von Besprechungskonfigurationseinstellungen.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Ändert die derzeit in Ihrer Organisation verwendeten Besprechungskonfigurationseinstellungen.  <br/> |
   
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
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Ruft Informationen dazu ab, wie Skype for Business Server reagiert, wenn Benutzer einer Einwahlkonferenz beitreten oder diese verlassen.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Gibt Informationen zu allen Zugriffsnummern für Einwahlkonferenzen zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Gibt die für Einwahlkonferenzen verwendeten DtmF-Signaleinstellungen (Dual-Tone Multifrequency) zurück. Mit DTMF können Benutzer, die sich in eine Konferenz einwählen, Konferenzeinstellungen (z. B. stummschalten und Stummschalten der eigenen Eigenen oder Sperren und Entsperren der Konferenz) über die Tastatur auf ihrem Telefon steuern.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Gibt eine Liste der Sprachen zurück, einschließlich Regional-/Minoritätssprachen, die für die Verwendung mit Skype for Business Server-Einwahlkonferenzen unterstützt werden. Diese Sprachen werden für die Übermittlung von Audionachrichten und Anweisungen für Benutzer verwendet, die mit einem Telefon an der Konferenz teilnehmen.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Gibt Informationen zu den in Ihrer Organisation verwendeten Wählplänen zurück.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Weist einem oder mehreren Benutzern oder Gruppen einen Wählplan zu.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importiert Konferenzverzeichnissen aus Microsoft Office Communications Server 2007 R2 in Skype for Business Server. Dadurch wird die Interoperabilität zwischen Skype for Business Server und Office Communications Server 2007 R2 ermöglicht.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Verschiebt ein vorhandenes Konferenzverzeichnis aus einem Pool in einen anderen. Konferenzverzeichnisse helfen den Benutzern von Einwahlkonferenzen beim Suchen nach Konferenzinformationen.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Erstellt ein neues Konferenzverzeichnis für die Verwendung in Ihrer Organisation. Konferenzverzeichnisse helfen den Benutzern von Einwahlkonferenzen beim Suchen nach Konferenzinformationen.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Erstellt eine neue Zugriffsnummer für Einwahlkonferenzen.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Erstellt eine neue Auflistung von Konfigurationseinstellungen für Einwahlkonferenzen. Diese Einstellungen bestimmen, wie Skype for Business Server reagiert, wenn Benutzer einer Einwahlkonferenz beitreten oder diese verlassen. Insbesondere werden Informationen darüber zurückgegeben, ob Teilnehmer ihren Namen aufzeichnen müssen, wenn sie einer Konferenz beitreten, und wie (oder ob) das System ansagt, dass jemand dem Anruf beigetreten ist oder diesen verlassen hat.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Erstellt eine neue Auflistung von DtmF-Signaleinstellungen (Dual-Tone Multifrequency), die für Einwahlkonferenzen verwendet werden.  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Erstellt einen neuen Wählplan.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Entfernt ein vorhandenes Konferenzverzeichnis. Konferenzverzeichnisse helfen den Benutzern von Einwahlkonferenzen beim Suchen nach Konferenzinformationen.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Entfernt eine vorhandene Zugriffsnummer für Einwahlkonferenzen.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Entfernt eine oder mehrere Auflistungen von Konfigurationseinstellungen für Einwahlkonferenzen. Diese Einstellungen bestimmen, wie Skype for Business Server reagiert, wenn Benutzer einer Einwahlkonferenz beitreten oder diese verlassen.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Entfernt eine vorhandene Auflistung von DtmF-Signaleinstellungen (Dual-Tone Multi-Frequency), die für Einwahlkonferenzen verwendet werden.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Ändert die Eigenschaftswerte einer vorhandenen Zugriffsnummer für Einwahlkonferenzen. Bei Einwahlkonferenzen können Benutzer mit einem "normalen" Telefon, einem Mobiltelefon oder einem anderen Gerät im Telefonfestnetz (Public Switched Telephone Network, PSTN) am Audioteil einer Konferenz teilnehmen.  <br/> |
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
   
**Andere Konferenzeinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |Deaktiviert einen Skype for Business Server-Besprechungsraum. Ein Besprechungsraum ist ein Konferenzmedium, das für Videokonferenzen und Szenarien der Zusammenarbeit in kleinen Konferenzräume entwickelt wurde. Wenn Sie ein Besprechungsraumobjekt deaktivieren, entfernen Sie alle Skype for Business Server-spezifischen Active Directory-Attribute, die dem Benutzerkonto zugewiesen sind, das den Besprechungsraum darstellt. Das Active Directory-Benutzerkonto wird allerdings nicht gelöscht.  <br/> |
|[Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |Aktiviert einen Skype for Business Server-Besprechungsraum. Zum Aktivieren eines Besprechungsraums müssen Sie zunächst ein Active Directory-Benutzerkonto erstellen, das dieses System repräsentiert. Beachten Sie, dass zwar Besprechungsraumobjekte auf Benutzerkonten basieren, diese Objekte jedoch nicht angezeigt werden, wenn Sie das cmdlet Get-CsUser ausführen.  <br/> |
|[Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |Gibt Informationen zu dem in Ihrer Organisation verwendeten Konferenzhaftungsausschluss zurück. Der Konferenzhaftungssausschluss ist eine Meldung, die Benutzern angezeigt wird, die der Konferenz über einen Link beitreten (z. B. Benutzer, die einen Konferenzlink in einen Browser wie Windows Internet Explorer einfügen).  <br/> |
|[Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |Gibt Informationen zu allen Skype for Business Server-Besprechungsräumen zurück, die für die Verwendung in der Organisation konfiguriert sind.  <br/> |
|[Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |Verschiebt ein Skype for Business Server-Besprechungsraumobjekt von einem Registrierungsstellenpool in einen anderen.  <br/> |
|[Remove-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |Löscht den Text aus dem Header und aus dem Hauptteil des in Ihrer Organisation verwendeten Konferenzhaftungsausschlusses. Der Konferenzhaftungssausschluss ist eine Meldung, die Benutzern angezeigt wird, die der Konferenz über einen Link beitreten (z. B. Benutzer, die einen Konferenzlink in einen Browser wie Windows Internet Explorer einfügen).  <br/> |
|[Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |Ändert die Eigenschaftswerte eines vorhandenen Skype for Business Server-Besprechungsraums.  <br/> |
   
**Testen von Einstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |Testet, ob ein Benutzerpaar an einer Konferenz zur Anwendungsfreigabe teilnehmen kann.  <br/> |
|[Test-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |Hiermit wird getestet, ob ein Benutzer eine Verbindung mit seinem Audiokonferenzanbieter herstellen kann. Bei einem Audiokonferenzanbieter handelt es sich um ein Drittanbieterunternehmen, das Konferenzdienste für Organisationen bereitstellt. Audiokonferenzanbieter bieten Benutzern u. a. die Möglichkeit, von außerhalb eines Standorts und ohne Verbindung mit dem Unternehmensnetzwerk oder dem Internet am Audioteil einer Konferenz oder Besprechung teilzunehmen.  <br/> |
|[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |Testet, ob ein Benutzerpaar an einer Audio-/Videokonferenz teilnehmen kann.  <br/> |
|[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |Überprüft, ob ein Benutzerpaar an einer Skype for Business Server-Webkonferenz teilnehmen kann, die Aktivitäten wie das Freigeben oder Anzeigen von PowerPoint-Folien, Whiteboards oder Abstimmungen umfasst. Das Cmdlet überprüft außerdem, ob der Skype for Business Server-Webkonferenzdienst Office Web Apps Server erkennen kann und ob ein Client eine PowerPoint-Datei für die Übertragung von Office Web Apps Server hochladen kann.  <br/> |
|[Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |Überprüft, ob ein Benutzer an einer Einwahlkonferenzsitzung teilnehmen kann.  <br/> |
|[Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |Testet einen Wählplan (ehemals als Standortprofil bezeichnet) für eine Telefonnummer und gibt die Normalisierungsregel, die auf diese Nummer angewendet wird, sowie die übersetzte Nummer nach dem Anwenden der Normalisierungsregel zurück.  <br/> |
|[Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |Testet, ob drei Benutzer an einer Skype for Business Server Mobility Service-Konferenz teilnehmen können. Der Mobilitätsdienst ermöglicht Benutzern von Mobiltelefonen wie iPhones und Windows Phones das Austauschen von Chatnachrichten und Anwesenheitsinformationen. Internes Speichern und Abrufen von Voicemail anstatt mit dem Drahtlosanbieter; und nutzen Sie Skype for Business Server-Funktionen wie Geschäftlich anrufen und Einwahlkonferenzen.  <br/> **Hinweis:** Clients, die MCX verwenden, werden in Skype for Business Server 2019 nicht unterstützt.|
|[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |Testet, ob ein Benutzerpaar eine Onlinekonferenz mit der Unified Communications Web API (UCWA) planen, beitreten und dann durchführen kann.  <br/> |
|[Debug-CsDataConference](https://docs.microsoft.com/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |Gibt Diagnoseinformationen für die in Skype for Business Server enthaltenen Datenkonferenzfunktionen zurück.  <br/> |
   

