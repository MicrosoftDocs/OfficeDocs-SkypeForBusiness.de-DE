---
title: Einrichten von Audiokonferenzen für Skype for Business
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Hier erfahren Sie, wie Sie Einwahl- oder Audiokonferenzen für Personen in Ihrem Unternehmen einrichten, die telefonisch an Konferenzanrufen teilnehmen müssen. '
ms.openlocfilehash: a36482dc6c58275491c65ac518e98cdc0ac0b787
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2019
ms.locfileid: "35792173"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a>Einrichten von Audiokonferenzen für Skype for Business

Manchmal müssen Mitarbeiter in Ihrer Organisation ein Telefon nutzen, um sich in eine Besprechung einzuwählen. Für genau diese Situation ist die Audiokonferenzfunktion in Skype for Business gedacht. Teilnehmer können sich mit einem Telefon in Skype for Business-Besprechungen einwählen, anstatt die Skype for Business-App auf einem Mobilgerät oder PC zu verwenden. 
  
You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Häufig gestellte Fragen zu Audiokonferenzen finden Sie unter [Häufig gestellte Fragen zu Audiokonferenzen](/MicrosoftTeams/audio-conferencing-common-questions).

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Schritt 1: Stellen Sie fest, ob Audiokonferenzen in Ihrem Land/Ihrer Region verfügbar sind
<a name="__top"> </a>

Gehen Sie auf [Länder- und Regionenverfügbarkeit für Audiokonferenzen und Anrufpläne](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) und wählen Sie Ihr Land oder Ihre Region aus, um Verfügbarkeitsinformationen über Audiokonferenzen sowie Informationen über Telefonanlage, Anrufpläne, gebührenfreie Nummern und Guthaben für Kommunikationen zu erhalten. 
 
## <a name="step-2-get-and-assign-licenses"></a>Schritt 2: Abrufen und Zuweisen von Lizenzen
 
1. Für Audiokonferenzen benötigen Sie eine Lizenz für jeden Benutzer, der Einwahlbesprechungen einrichten wird. Informationen darüber, welche Lizenzen Sie für Audiokonferenzen erwerben müssen und wie viel sie kosten, finden Sie unter [Lizenzierung des Skype for Business-Add-Ons](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    >[!NOTE] 
    > Audiokonferenzen sind in Office 365 Enterprise E5-Lizenzen und als Add-On enthalten.
        
2. Nachdem Sie die Audiokonferenz-Lizenzen erworben haben, müssen Sie diese den Personen in Ihrer Organisation zuweisen, die Besprechungen planen oder leiten werden. Siehe [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) an die Mitarbeiter in Ihrer Organisation, die Besprechungen planen oder leiten werden.
    
3. Wir empfehlen auch, dass Sie Guthaben für Kommunikations-Lizenzen (sie kosten nichts) denselben Personen zuweisen, denen Sie im vorherigen Schritt Lizenzen zugewiesen haben. Weitere Informationen zum Guthaben für Kommunikationen finden Sie unter [Einrichten von Guthaben für Kommunikationen für Ihr Unternehmen](/microsoftteams/set-up-communications-credits-for-your-organization).
    
> [!NOTE]
> Sie können auch [Audiokonferenzen mit Minutenabrechnung](/microsoftteams/audio-conferencing-pay-per-minute) einrichten.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Schritt 3: Servicenummern für Ihre Konferenzbrücken anfordern
<a name="__top"> </a>

Für Audiokonferenzen können Sie keine Benutzertelefonnummern verwenden; Sie müssen Servicenummern anfordern. Sie können für Ihre Konferenzbrücken gebührenpflichtige oder gebührenfreie Servicenummern abrufen. Es gibt drei Möglichkeiten, gebührenpflichtige und gebührenfreie Servicenummern zu erhalten: 
  
- **Verwenden des Skype for Business Admin Centers**. Für einige Länder/Regionen können Sie Servicenummern für Ihre Konferenzbrücken über das Skype for Business Admin Center erhalten. Siehe [Abrufen von Servicetelefonnummern](/microsoftteams/getting-service-phone-numbers).
    
- **Portieren von bestehenden Servicenummern**. Portieren oder übertragen Sie vorhandene Telefonnummern von Ihrem derzeitigen Dienstanbieter oder Netzbetreiber zu Office 365. Über [Übertragen von Telefonnummern zu Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) oder [Rufnummern für Ihre Organisation verwalten](/microsoftteams/manage-phone-numbers-for-your-organization) erhalten Sie weitere hilfreiche Informationen.  
  
- **Verwenden eines Anforderungsformulars für neue Telefonnummern**. Manchmal können Sie (je nach Land/Region) Ihre neuen Servicenummern nicht über das Skype for Business Admin Center beziehen, oder Sie benötigen bestimmte Telefonnummern oder Ortsvorwahlen. Wenn dies der Fall ist, müssen Sie ein Formular herunterladen und an uns zurücksenden. Weitere Informationen finden Sie unter [Verwalten von Rufnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Schritt 4: Zuweisen einer Servicenummer zur Konferenzbrücke
<a name="__top"> </a>

Sobald Sie Ihre gebührenpflichtigen und/oder gebührenfreien Telefonnummern für Ihre Konferenzbrücke erhalten, müssen Sie die Nummern zuweisen, damit sie für die Einladungen zu den Besprechungen verwendet werden können.  

So weisen Sie Ihrer Audiokonferenzbrücke eine neue Rufnummer zu:

![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers:**

 1. Wechselns Sie zum **Microsoft 365 Admin Center** > **Admin Center** > **Teams** > **Altes Portal**.
 2. Wählen Sie **Anruf** > **Telefonnummern** aus.
 3. Wählen Sie die entsprechende Telefonnummer aus, und klicken Sie auf **Zuweisen**.

Weitere Informationen finden Sie unter [Ändern der Telefonnummern Ihrer Audiokonferenzbrücke](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Schritt 5: Legen Sie die Standard- und Alternativsprachen für eine Konferenzbrücke fest
<a name="__top"> </a>

Als Nächstes sollten Sie die [Sprachen für die automatische Telefonzentrale für Audiokonferenzen festlegen](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md), die die automatische Telefonkonferenzzentrale verwendet, um einen Anrufer zu begrüßen, wenn er sich mit einer Telefonnummer für Audiokonferenzen einwählt. 

![Ein Symbol mit dem Microsoft Teams-Logo](../images/teams-logo-30x30.png) **Unter Verwendung des Microsoft Teams Admin Centers**:

1. Wechseln Sie über das Dashboard zu **Besprechungen** > **Konferenzbrücken**.
2. Wählen Sie die Telefonnummer der Konferenzbrücke, klicken Sie auf **Bearbeiten**, und wählen Sie dann die Standardsprache.

![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**:

1. Wechselns Sie zum Admin Center > **Admin Center** > **Teams** > **Altes Portal**.
2. WählenSie **Audiokonferenzen** > **Microsoft Bridge** aus. 
3. Wählen Sie die Telefonnummer der Konferenzbrücke, klicken Sie auf **Sprachen festlegen**, und wählen Sie dann die Standardsprache aus.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Schritt 6: Servicenummern für Ihre Konferenzbrücken einstellen
<a name="__top"> </a>
    
Nachdem Sie Ihre Konferenzbrücke eingerichtet haben, vergewissern Sie sich, dass die Standardeinstellungen, wie z. B. Ein-/Ausgangsbenachrichtigungen und PIN-Länge, die sind, die Sie verwenden möchten; wenn nicht, können Sie sie ändern. 

![Ein Symbol mit dem Microsoft Teams-Logo](../images/teams-logo-30x30.png) **Unter Verwendung des Microsoft Teams Admin Centers**:

1. Wechseln Sie über das Dashboard zu **Besprechungen** > **Konferenzbrücken**.
2. Wählen Sie **Brückeneinstellungen** aus. Der **Brücke**-Einstellungsbereich wird geöffnet. 

Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers:**

1. Wechselns Sie zum **Microsoft 365 Admin Center** > **Admin Center** > **Teams** > **Altes Portal**.
2. WählenSie **Audiokonferenzen** > **Einstellungen von Microsoft Bridge** aus. Die Seite **Microsoft Brückeneinstellungen** wird geöffnet. 

Weitere Informationen finden Sie unter [Einstellungen für eine Audiokonferenzbrücke ändern](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Schritt 7: Zuweisen von Einwahlnummern für Benutzer, die Besprechungen leiten

Nachdem Sie eine Audiokonferenzbrücke erstellt haben, müssen Sie die gebührenpflichtigen und gebührenfreien Nummern für Ihre Benutzer festlegen.

Sie müssen dies für alle Personen in Ihrer Organisation tun, die Besprechungen leiten oder planen. 

![Ein Symbol mit dem Microsoft Teams-Logo](../images/teams-logo-30x30.png) **Unter Verwendung des Microsoft Teams Admin Centers**:

1. Klicken Sie im Dashboard auf **Benutzer**, wählen Sie den entsprechenden Benutzer aus der Liste aus, und klicken Sie dann auf **Bearbeiten**.
2. Klicken Sie neben **Audiokonferenzen** auf **Bearbeiten**, und wählen Sie dann im Bereich **Audiokonferenzen** eine Nummer aus den Listen der **gebührenpflichtigen** und **gebührenfreien** Telefonnummern aus.

![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers:**

1. Wechselns Sie zum **Microsoft 365 Admin Center** > **Teams** > **Altes Portal**.
2. Wählen Sie **Audiokonferenzen** > **Benutzer**, wählen Sie Benutzer aus der Liste aus, und klicken Sie dann auf **Bearbeiten**. 

Weitere Informationen finden Sie unter [Zuweisen von Microsoft als Anbieter von Audiokonferenzen](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Schritt 8: Besprechungseinladungen einrichten (optional)
<a name="__top"> </a>
 
Die für den Nutzer festgelegten Einwahlnummern werden automatisch den Besprechungseinladungen hinzugefügt, die Besprechungsteilnehmern zugesendet werden. Sie können jedoch Ihre eigenen Hilfe- und rechtliche Links, eine SMS und eine kleine Firmengrafik hinzufügen, wenn Sie möchten. Siehe [Anpassen von Besprechungseinladungen](../set-up-skype-for-business-online/customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Verwandte Themen

[Allgemeine Fragen zu Audiokonferenzen](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Einrichten von Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Telefonnummern für Audiokonferenzen](phone-numbers-for-audio-conferencing.md)
  
[Festlegen von Optionen für Onlinebesprechungen und Telefonkonferenzen](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
