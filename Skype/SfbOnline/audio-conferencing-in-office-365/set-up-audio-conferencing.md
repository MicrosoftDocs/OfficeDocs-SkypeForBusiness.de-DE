---
title: Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Informationen Sie zum Einrichten von einwählen oder audio-Konferenzen für die Personen in Ihrem Unternehmen, die zum Teilnehmen an Telefonkonferenzen mit einem Telefon benötigen. '
ms.openlocfilehash: 3ac6b6dbe562b7aff14394b5dbd2888ce04eb1c7
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887951"
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams

Manchmal müssen Personen in Ihrer Organisation ein Telefon nutzen, um sich in eine Besprechung einzuwählen. Skype für Unternehmen und die Microsoft-Teams, gehören die Audiokonferenzen nur in dieser Situation! Personen können Skype für Business oder Microsoft-Teams, Besprechungen, die mit einem Telefon ein, anstatt die Skype für Business oder Microsoft-Teams app auf einem mobilen Gerät oder PC anrufen. 
  
Sie müssen nur eingerichtet werden Audiokonferenz für die Personen, die das Planen, oder führen Besprechungen planen. Besprechungsteilnehmer, die sich einwählen, benötigen keine ihnen zugewiesenen Lizenzen oder andere Einstellungen.
  
Häufig gestellte Fragen zu Audiokonferenzen finden Sie unter [Häufig gestellte Fragen zu Audiokonferenzen](/MicrosoftTeams/audio-conferencing-common-questions).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Schritt 1: Stellen Sie fest, ob Audiokonferenzen in Ihrem Land/Ihrer Region verfügbar sind
<a name="__top"> </a>


Gehen Sie auf [Länder- und Regionenverfügbarkeit für Audiokonferenzen und Anrufpläne](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) und wählen Sie Ihr Land oder Ihre Region aus, um Verfügbarkeitsinformationen über Audiokonferenzen sowie Informationen über Telefonanlage, Anrufpläne, gebührenfreie Nummern und Guthaben für Kommunikationen zu erhalten. 
 
## <a name="step-2-get-and-assign-licenses"></a>Schritt 2: Abrufen und Zuweisen von Lizenzen
 
1. Für Audiokonferenzen benötigen Sie eine Lizenz für jeden Benutzer, der Einwahlbesprechungen einrichtet. Welche Lizenzen finden Sie kaufen für Audiokonferenzen und wie viel Kosten werden müssen, finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Add-On-Lizenzierung](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
        
2. Nachdem Sie die Audiokonferenz-Lizenzen erworben haben, müssen Sie diese den Personen in Ihrer Organisation zuweisen, die Besprechungen planen oder leiten werden. Finden Sie unter [zuweisen oder Entfernen von Lizenzen für Office 365 für Unternehmen](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) Sie erworben haben, um die Personen in Ihrer Organisation, die Besprechungen planen oder Lead gesendet werden.
    
3. Wir empfehlen auch, dass Sie Guthaben für Kommunikations-Lizenzen (sie kosten nichts) denselben Personen zuweisen, denen Sie im vorherigen Schritt Lizenzen zugewiesen haben. Weitere Informationen zum Guthaben für Kommunikationen finden Sie unter [Einrichten von Guthaben für Kommunikationen für Ihr Unternehmen](/microsoftteams/set-up-communications-credits-for-your-organization).
    
> [!NOTE]
> Sie können auch pay-per-minute Audiokonferenzen einrichten. Klicken Sie [hier](/microsoftteams/audio-conferencing-pay-per-minute), um weitere Informationen zu deren Verwendung zu erhalten.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Schritt 3: Servicenummern für Ihre Konferenzbrücken anfordern
<a name="__top"> </a>

Für Audiokonferenzen können Sie keine Benutzertelefonnummern verwenden; Sie müssen Servicenummern anfordern. Sie können für Ihre Konferenzbrücken gebührenpflichtige oder gebührenfreie Servicenummern abrufen. Es gibt drei Möglichkeiten, gebührenpflichtige und gebührenfreie Servicenummern zu erhalten: 
  
- **Verwenden Sie die Skype für Business Administrationscenter.** Für einige Länder/Regionen können Sie Servicenummern für Ihre Konferenzbrücken über das Skype for Business Admin Center erhalten, siehe [Servicetelefonnummern erhalten](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
    
- **Port Ihrer vorhandenen Dienst Rufnummern.** Port oder Nummern zu Office 365 aus Ihrer aktuellen Dienstanbieter oder Mobilfunkbetreibers übertragen. Über [Übertragen von Telefonnummern zu Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) oder [Rufnummern für Ihre Organisation verwalten](/microsoftteams/manage-phone-numbers-for-your-organization) erhalten Sie weitere hilfreiche Informationen.  
  
- **Verwenden Sie ein Anforderungsformular für neue Nummern.** In einigen Fällen (je nach Ihrem Land/Region) nicht um Ihre neue Dienst Rufnummern, die mit der Skype für Business Administrationscenter zu erhalten, oder benötigen Sie bestimmte Telefonnummern oder Ortskennzahlen. In diesem Fall müssen Sie ein Formular herunterladen und an uns senden. Weitere Informationen finden Sie unter [Verwalten von Rufnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Schritt 4: Zuweisen einer Servicenummer zur Konferenzbrücke
<a name="__top"> </a>

Sobald Sie Ihre gebührenpflichtige und/oder gebührenfreien Telefonnummern für Ihre Konferenzbrücke erhalten, müssen Sie die Nummern zuweisen, damit sie für die Einladungen zu den Besprechungen verwendet werden können.  

Um eine neue Rufnummer Ihrer Audiokonferenzbrücke zuzuweisen:

![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter:**

 Wechseln Sie zu der **Office 365 Admin Center** > **Admin Centers** > **Skype für Unternehmen** > **VoIP** > **Telefonnummern**, wählen Sie die Rufnummer ein, und klicken Sie auf **zuweisen**.

Weitere Informationen finden Sie unter [Ändern der Telefonnummern Ihrer Audiokonferenzbrücke](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Schritt 5: Legen Sie die Standard- und Alternativsprachen für eine Konferenzbrücke fest
<a name="__top"> </a>

Als Nächstes möchten Sie [Auto-Attendant-Sprachen für Audiokonferenzen einstellen](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md), die der Auto-Attendant verwendet, um einen Anrufer zu begrüßen, wenn er sich mit einer Telefonnummer für Audiokonferenzen einwählt. 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Verwendung der Microsoft-Teams und Skype for Business Admin Center:**

Gehen Sie im Dashboard auf**Besprechungen** > **Konferenzbrücken**, wählen Sie die Telefonnummer der Konferenzbrücke, klicken Sie auf **Bearbeiten**, und wählen Sie dann die Standardsprache.

![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter:**

Wechseln Sie auf **Office 365 Admin Center** > **Admin Centers** > **Skype für Business** > **Audiokonferenzen** > **Microsoft Brückeneinstellungen**, wählen Sie die Telefonnummer der Konferenzbrücke und klicken Sie dann auf **Sprachen einstellen**.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Schritt 6: Servicenummern für Ihre Konferenzbrücken einstellen
<a name="__top"> </a>
    
Nachdem Sie Ihre Konferenzbrücke eingerichtet haben, vergewissern Sie sich, dass die Standardeinstellungen, wie z. B. Ein-/Ausgangsbenachrichtigungen und PIN-Länge, die sind, die Sie verwenden möchten; wenn nicht, können Sie sie ändern. 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Verwendung der Microsoft-Teams und Skype for Business Admin Center:**

Wechseln Sie über das Dashboard auf **Besprechungen** > **Konferenzbrücken** > **Brückeneinstellungen**. Der **Brücke**-Einstellungsbereich wird geöffnet. Weitere Informationen finden Sie unter [Einstellungen für eine Audiokonferenzbrücke ändern](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter:**

Wechseln Sie auf **Office 365 Admin Center** > **Admin Centers** > **Skype für Business** > **Audiokonferenzen** > **Microsoft Brückeneinstellungen**. Die Seite **Microsoft Brückeneinstellungen** wird geöffnet. Weitere Informationen finden Sie unter [Einstellungen für eine Audiokonferenzbrücke ändern](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Schritt 7: Zuweisen von Einwahlnummern für Benutzer, die Besprechungen leiten

Nachdem Sie eine Audiokonferenzbrücke erstellt haben, müssen Sie die gebührenpflichtigen und gebührenfreien Nummern für Ihre Benutzer festlegen.

Sie müssen dies für alle Personen in Ihrer Organisation tun, die Besprechungen leiten oder planen. Gehen Sie dazu so vor:

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Verwendung der Microsoft-Teams und Skype for Business Admin Center:**

Klicken Sie aus dem Dashboard auf **Benutzer**, wählen Sie den Benutzer aus der Liste, klicken Sie auf **Bearbeiten**, klicken Sie auf **Bearbeiten**, neben **Audiokonferenzen**und wählen Sie dann im Bereich **Audiokonferenzen** eine Nummer für die **gebührenpflichtige** und **gebührenfreie** Liste der Telefonummern.

![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter:**

Wechseln Sie auf **Office 365 Admin Center** > **Skype für Business** > **Audiokonferenzen** > **Benutzer**, wählen Sie Benutzer aus der Liste aus, und klicken Sie auf **Bearbeiten**. Weitere Informationen finden Sie unter [Zuweisen von Microsoft als Anbieter von Audiokonferenzen](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Schritt 8: Besprechungseinladungen einrichten (optional)
<a name="__top"> </a>
 
Die Einwahlnummern, die für den Benutzer festgelegt sind werden automatisch der besprechungseinladungen hinzugefügt werden, die an die Besprechungsteilnehmer gesendet werden. Sie können jedoch Ihre eigenen Hilfe- und rechtliche Links, eine SMS und eine kleine Firmengrafik hinzufügen, wenn Sie möchten. Finden Sie unter [Anpassen von besprechungseinladungen](../set-up-skype-for-business-online/customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Verwandte Themen

[Allgemeine Fragen zu Audiokonferenz](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Einrichten von Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Telefonnummern für Audiokonferenzen](phone-numbers-for-audio-conferencing.md)
  
[Optionen für Onlinebesprechungen und Telefonkonferenzen festlegen](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
