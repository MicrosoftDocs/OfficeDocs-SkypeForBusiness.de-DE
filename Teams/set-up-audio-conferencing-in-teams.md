---
title: Einrichten von Audiokonferenzen für Microsoft-Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Informationen Sie zum Einrichten von einwählen oder Audiokonferenz für die Personen in Ihrem Unternehmen, die ein Telefon zum Teilnehmen an Telefonkonferenzen verwenden müssen. '
ms.openlocfilehash: 30e79282f04c2d1b4dc7ff01673461b7a18254fd
ms.sourcegitcommit: 188c57e6b6c707edb694bb922556dea1c4724846
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2019
ms.locfileid: "30955030"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>Einrichten von Audiokonferenzen für Microsoft-Teams

Manchmal müssen Personen in Ihrer Organisation ein Telefon nutzen, um sich in eine Besprechung einzuwählen. Microsoft-Teams, enthält das Feature Audiokonferenzen nur in dieser Situation! Personen können Teams Besprechungen mit einem Telefon ein, anstatt die Teams app auf einem mobilen Gerät oder PC anrufen. 
  
Sie müssen Audiokonferenzen nur für Personen einrichten, die Besprechungen planen oder leiten möchten. Besprechungsteilnehmer, die sich einwählen, benötigen keine ihnen zugewiesenen Lizenzen oder andere Einstellungen.
  
Häufig gestellte Fragen zu Audiokonferenzen finden Sie unter [Häufig gestellte Fragen zu Audiokonferenzen](audio-conferencing-common-questions.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Schritt 1: Stellen Sie fest, ob Audiokonferenzen in Ihrem Land/Ihrer Region verfügbar sind
<a name="__top"> </a>

Gehen Sie auf [Länder- und Regionenverfügbarkeit für Audiokonferenzen und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) und wählen Sie Ihr Land oder Ihre Region aus, um Verfügbarkeitsinformationen über Audiokonferenzen sowie Informationen über Telefonanlage, Anrufpläne, gebührenfreie Nummern und Guthaben für Kommunikationen zu erhalten. 
 
## <a name="step-2-get-and-assign-licenses"></a>Schritt 2: Abrufen und Zuweisen von Lizenzen
 
1. Für Audiokonferenzen benötigen Sie eine Lizenz für jeden Benutzer, der Einwahlbesprechungen einrichtet. Welche Lizenzen finden Sie kaufen für Audiokonferenzen und wie viel Kosten werden müssen, finden Sie unter [Microsoft-Teams, Add-On-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

    >[!NOTE] 
    > Audiokonferenzen ist in Office 365 Enterprise E5 Lizenzen und als Add-on enthalten.
        
2. Nachdem Sie die Audiokonferenz Lizenzen erwerben möchten, müssen Sie diese Personen in Ihrer Organisation zu planen, oder führen Besprechungen, die zuordnen. Finden Sie unter [Zuweisen von Lizenzen für Benutzer in Office 365 für Unternehmen](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) Sie erworben haben, um die Personen in Ihrer Organisation, die Besprechungen planen oder Lead gesendet werden.
    
3. Wir empfehlen auch, dass Sie Guthaben für Kommunikations-Lizenzen (sie kosten nichts) denselben Personen zuweisen, denen Sie im vorherigen Schritt Lizenzen zugewiesen haben. Weitere Informationen zum Guthaben für Kommunikationen finden Sie unter [Einrichten von Guthaben für Kommunikationen für Ihr Unternehmen](set-up-communications-credits-for-your-organization.md).
    
> [!NOTE]
> Sie können auch [Audiokonferenzen Bezahlung pro Minute](audio-conferencing-pay-per-minute.md)einrichten.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Schritt 3: Servicenummern für Ihre Konferenzbrücken anfordern
<a name="__top"> </a>

Für Audiokonferenzen können Sie keine Benutzertelefonnummern verwenden; Sie müssen Servicenummern anfordern. Sie können für Ihre Konferenzbrücken gebührenpflichtige oder gebührenfreie Servicenummern abrufen. Es gibt drei Möglichkeiten, gebührenpflichtige und gebührenfreie Servicenummern zu erhalten: 
  
- **Mithilfe der Verwaltungskonsole von Microsoft-Teams**. Für einige Länder/Regionen können Sie Service Zahlen für Ihre Konferenzbrücken mithilfe der Verwaltungskonsole von Microsoft-Teams, abrufen. Finden Sie unter [Getting Service Rufnummern](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).
    
- **Port Ihrer vorhandenen Dienst Rufnummern**. Port oder Nummern zu Office 365 aus Ihrer aktuellen Dienstanbieter oder Mobilfunkbetreibers übertragen. Über [Übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md) oder [Rufnummern für Ihre Organisation verwalten](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) erhalten Sie weitere hilfreiche Informationen.  
  
- **Verwenden einer Anforderungsformular für neue Nummern**. In einigen Fällen (je nach Ihrem Land/Region) nicht um Ihre neue Dienst Rufnummern, die mit dem Microsoft-Teams, Administrationscenter zu erhalten, oder benötigen Sie bestimmte Telefonnummern oder Ortskennzahlen. In diesem Fall müssen Sie ein Formular herunterladen und an uns senden. Weitere Informationen finden Sie unter [Verwalten von Rufnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Schritt 4: Zuweisen einer Servicenummer zur Konferenzbrücke
<a name="__top"> </a>

Nachdem Sie Ihre gebührenpflichtige und/oder gebührenfreien Telefonnummern für Ihre Konferenzbrücke erhalten, müssen Sie die Zahlen zuweisen, damit sie für besprechungseinladungen verwendet werden können.  

Befolgen Sie diese Stesps eine neue Rufnummer ein, um Ihre audiokonferenzbrücke zuzuweisen.

![SFB-Logo-30x30.png](media/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter:**

 1. Wechseln Sie zu der **Microsoft-365-Verwaltungskonsole** > **Admin zentriert** > **Teams** > **Legacy-Portal**.
 2. Wählen Sie **Stimme** > **Rufnummern**.
 3. Wählen Sie die Rufnummer ein, und klicken Sie auf **zuweisen**.

Weitere Informationen finden Sie unter [Ändern der Rufnummern Ihrer Audio Konferenzbrücke](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Schritt 5: Legen Sie die Standard- und Alternativsprachen für eine Konferenzbrücke fest
<a name="__top"></a> Im nächsten Schritt [Legen Sie automatische Telefonzentrale Sprachen für Audiokonferenzen in Microsoft-Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) , die automatische konferenzzentrale zum Anrufer begrüßen, wenn sie eine Rufnummer für Audiokonferenzen in einwählen verwendet, werden soll. 

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**:

1. Das Dashboard, wechseln Sie zu **Besprechungen** > **Konferenzbrücken**.
2. Wählen Sie die Live Meeting-Brücke Telefonnummer aus, klicken Sie auf **Bearbeiten**, und wählen Sie dann die Standardsprache.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Schritt 6: Servicenummern für Ihre Konferenzbrücken einstellen
<a name="__top"> </a>
    
Nachdem Sie Ihre Konferenzbrücke eingerichtet haben, vergewissern Sie sich, dass die Standardeinstellungen, wie z. B. Ein-/Ausgangsbenachrichtigungen und PIN-Länge, die sind, die Sie verwenden möchten; wenn nicht, können Sie sie ändern. 

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**:

1. Das Dashboard, wechseln Sie zu **Besprechungen** > **Konferenzbrücken**.
2. Wählen Sie **Bridge Einstellungen**aus. Der **Brücke**-Einstellungsbereich wird geöffnet. 

Weitere Informationen finden Sie unter [Einstellungen für eine Audiokonferenzbrücke ändern](change-the-settings-for-an-audio-conferencing-bridge.md).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Schritt 7: Zuweisen von Einwahlnummern für Benutzer, die Besprechungen leiten

Nachdem Sie eine Audiokonferenzbrücke erstellt haben, müssen Sie die gebührenpflichtigen und gebührenfreien Nummern für Ihre Benutzer festlegen.

Sie müssen dies für alle Personen in Ihrer Organisation tun, die Besprechungen leiten oder planen. 

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**:

1. Klicken Sie auf **Benutzer**aus dem Dashboard, wählen Sie den Benutzer aus der Liste, und wählen Sie **Bearbeiten**.
2. Wählen Sie neben **Audiokonferenzen** **Bearbeiten** , und wählen Sie dann im Bereich **Audiokonferenzen** eine Zahl in den **die gebührenpflichtige Telefonnummer** und **gebührenfreie** Nummern Listen.

Weitere Informationen finden Sie unter [Zuweisen von Microsoft als Anbieter von Audiokonferenzen](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Schritt 8: Besprechungseinladungen einrichten (optional)
<a name="__top"> </a>
 
Die Einwahlnummern, die für den Benutzer festgelegt sind werden automatisch der besprechungseinladungen hinzugefügt werden, die an die Besprechungsteilnehmer gesendet werden. Sie können jedoch Ihre eigenen Hilfe- und rechtliche Links, eine SMS und eine kleine Firmengrafik hinzufügen, wenn Sie möchten. Finden Sie unter [Anpassen von besprechungseinladungen](customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Verwandte Themen

[Allgemeine Fragen zu Audiokonferenzen](audio-conferencing-common-questions.md)
  
[Telefonnummern für Audiokonferenzen in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md)
  
[Optionen für Onlinebesprechungen und Telefonkonferenzen festlegen](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
