---
title: Einrichten von Audiokonferenzen für Microsoft Teams
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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Hier erfahren Sie, wie Sie Einwahl-oder Audiokonferenzen für die Personen in Ihrem Unternehmen einrichten, die ein Telefon für die Teilnahme an Konferenzgesprächen verwenden müssen. '
ms.openlocfilehash: 9fc9369b8dd2d7054ce7a2c1508dbc73eff3dfa9
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2019
ms.locfileid: "34432817"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>Einrichten von Audiokonferenzen für Microsoft Teams

Manchmal müssen Personen in Ihrer Organisation ein Telefon nutzen, um sich in eine Besprechung einzuwählen. Microsoft Teams enthält das Feature "Audiokonferenz" für nur diese Situation! Personen können mit einem Telefon in Teams-Besprechungen anrufen, anstatt die Teams-App auf einem mobilen Gerät oder PC zu verwenden. 
  
Sie müssen Audiokonferenzen nur für Personen einrichten, die Besprechungen planen oder leiten möchten. Besprechungsteilnehmer, die sich einwählen, benötigen keine ihnen zugewiesenen Lizenzen oder andere Einstellungen.
  
Häufig gestellte Fragen zu Audiokonferenzen finden Sie unter [Häufig gestellte Fragen zu Audiokonferenzen](audio-conferencing-common-questions.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Schritt 1: Stellen Sie fest, ob Audiokonferenzen in Ihrem Land/Ihrer Region verfügbar sind
<a name="__top"> </a>

Gehen Sie auf [Länder- und Regionenverfügbarkeit für Audiokonferenzen und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) und wählen Sie Ihr Land oder Ihre Region aus, um Verfügbarkeitsinformationen über Audiokonferenzen sowie Informationen über Telefonanlage, Anrufpläne, gebührenfreie Nummern und Guthaben für Kommunikationen zu erhalten. 
 
## <a name="step-2-get-and-assign-licenses"></a>Schritt 2: Abrufen und Zuweisen von Lizenzen
 
1. Für Audiokonferenzen benötigen Sie eine Lizenz für jeden Benutzer, der Einwahlbesprechungen einrichtet. Wenn Sie wissen möchten, welche Lizenzen Sie für Audiokonferenzen kaufen müssen und wie viel Sie Kosten werden, lesen Sie [Microsoft Teams-Add-on-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

    >[!NOTE] 
    > Audiokonferenzen sind in Office 365 Enterprise E5-Lizenzen und als Add-on enthalten.
        
2. Nachdem Sie die Audiokonferenz-Lizenzen gekauft haben, müssen Sie diese den Personen in Ihrer Organisation zuweisen, die Besprechungen planen oder leiten. Weitere Informationen finden Sie unter [Zuweisen von Lizenzen zu Benutzern in Office 365 für Unternehmen](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) , die Sie für die Personen in Ihrer Organisation erworben haben, die Besprechungen planen oder leiten.
    
3. Wir empfehlen auch, dass Sie Guthaben für Kommunikations-Lizenzen (sie kosten nichts) denselben Personen zuweisen, denen Sie im vorherigen Schritt Lizenzen zugewiesen haben. Weitere Informationen zum Guthaben für Kommunikationen finden Sie unter [Einrichten von Guthaben für Kommunikationen für Ihr Unternehmen](set-up-communications-credits-for-your-organization.md).
    
> [!NOTE]
> Sie können auch eine [Pay-per-Minute](audio-conferencing-pay-per-minute.md)-Audiokonferenz einrichten.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Schritt 3: Servicenummern für Ihre Konferenzbrücken anfordern
<a name="__top"> </a>

Für Audiokonferenzen können Sie keine Benutzertelefonnummern verwenden; Sie müssen Servicenummern anfordern. Sie können für Ihre Konferenzbrücken gebührenpflichtige oder gebührenfreie Servicenummern abrufen. Es gibt drei Möglichkeiten, gebührenpflichtige und gebührenfreie Servicenummern zu erhalten: 
  
- **Verwenden Sie das Microsoft Teams Admin Center**. In einigen Ländern/Regionen können Sie mithilfe des Microsoft Teams Admin Center Servicenummern für Ihre Konferenz Brücken abrufen. Weitere Informationen finden Sie unter [Abrufen von Telefonnummern für Dienstleistungen](/microsoftteams/getting-service-phone-numbers).
    
- **Portieren Sie Ihre vorhandenen Servicenummern**. Zum Portieren oder übertragen vorhandener Nummern von Ihrem aktuellen Dienstanbieter oder Telefonnetzbetreiber zu Office 365 Über [Übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md) oder [Rufnummern für Ihre Organisation verwalten](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) erhalten Sie weitere hilfreiche Informationen.  
  
- **Verwenden Sie ein Anforderungsformular für neue Nummern**. Manchmal (je nach Land/Region) können Sie Ihre neuen Dienstnummern nicht über das Microsoft Teams Admin Center abrufen, oder Sie benötigen bestimmte Telefonnummern oder Ortsvorwahl. In diesem Fall müssen Sie ein Formular herunterladen und an uns senden. Weitere Informationen finden Sie unter [Verwalten von Rufnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Schritt 4: Zuweisen einer Servicenummer zur Konferenzbrücke
<a name="__top"> </a>

Nachdem Sie Ihre gebührenpflichtigen und/oder gebührenfreien Telefonnummern für Ihre Konferenzbrücke erhalten haben, müssen Sie die Nummern zuweisen, damit Sie für Besprechungseinladungen verwendet werden können.  

Führen Sie die folgenden Schritte aus, um ihrer Audiokonferenz-Brücke eine neue Telefonnummer zuzuweisen.

![Ein Symbol mit dem Skype for Business-](media/sfb-logo-30x30.png) Logo **im Skype for Business Admin Center:**

 1. Wechseln Sie zum **Microsoft 365 Admin Center** > **Admin** > Center**Teams** > **Legacy-Portal**.
 2. Wählen Sie **VoIP** > ****-Rufnummern aus.
 3. Wählen Sie die Telefonnummer aus, und klicken Sie auf **zuweisen**.

Weitere Informationen finden Sie unter [Ändern der Telefonnummern auf der Audiokonferenz-Brücke](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Schritt 5: Legen Sie die Standard- und Alternativsprachen für eine Konferenzbrücke fest
<a name="__top"></a> Als nächstes möchten Sie die [Sprachen der automatischen Telefonzentrale für Audiokonferenzen in Microsoft Teams fest legen](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) , die von der automatischen Telefonzentrale für Konferenzen verwendet werden, um Anrufer zu grüßen, wenn Sie sich bei einer Telefonnummer für Audiokonferenzen einwählen. 

![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png) -Logo **mit dem Microsoft Teams Admin Center**zeigt:

1. Wechseln Sie im Dashboard zu **Besprechungen** > **Konferenz Brücken**.
2. Wählen Sie die Telefonnummer der Konferenzbrücke aus, klicken Sie auf **Bearbeiten**, und wählen Sie dann die Standardsprache aus.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Schritt 6: Servicenummern für Ihre Konferenzbrücken einstellen
<a name="__top"> </a>
    
Nachdem Sie Ihre Konferenzbrücke eingerichtet haben, vergewissern Sie sich, dass die Standardeinstellungen, wie z. B. Ein-/Ausgangsbenachrichtigungen und PIN-Länge, die sind, die Sie verwenden möchten; wenn nicht, können Sie sie ändern. 

![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png) -Logo **mit dem Microsoft Teams Admin Center**zeigt:

1. Wechseln Sie im Dashboard zu **Besprechungen** > **Konferenz Brücken**.
2. Wählen Sie **Brücken Einstellungen**aus. Der **Brücke**-Einstellungsbereich wird geöffnet. 

Weitere Informationen finden Sie unter [Einstellungen für eine Audiokonferenzbrücke ändern](change-the-settings-for-an-audio-conferencing-bridge.md).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Schritt 7: Zuweisen von Einwahlnummern für Benutzer, die Besprechungen leiten

Nachdem Sie eine Audiokonferenzbrücke erstellt haben, müssen Sie die gebührenpflichtigen und gebührenfreien Nummern für Ihre Benutzer festlegen.

Sie müssen dies für alle Personen in Ihrer Organisation tun, die Besprechungen leiten oder planen. 

![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png) -Logo **mit dem Microsoft Teams Admin Center**zeigt:

1. Klicken Sie im Dashboard auf **Benutzer**, wählen Sie den Benutzer in der Liste aus, und wählen Sie **Bearbeiten**aus.
2. Wählen Sie neben **Audio-Conferencing**die Option **Bearbeiten** aus, und wählen Sie dann im Bereich Audiokonferenz eine Nummer in den Listen **gebührenpflichtige** Nummer und **gebührenfreie** Nummern aus. ****

Weitere Informationen finden Sie unter [Zuweisen von Microsoft als Anbieter von Audiokonferenzen](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Schritt 8: Besprechungseinladungen einrichten (optional)
<a name="__top"> </a>
 
Die für den Benutzer festgelegten Einwahlnummern werden automatisch zu den Besprechungseinladungen hinzugefügt, die an Besprechungsteilnehmer gesendet werden. Sie können jedoch Ihre eigenen Hilfe- und rechtliche Links, eine SMS und eine kleine Firmengrafik hinzufügen, wenn Sie möchten. Weitere Informationen finden Sie unter [Anpassen von Besprechungseinladungen](customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Verwandte Themen

[Allgemeine Fragen zu Audiokonferenzen](audio-conferencing-common-questions.md)
  
[Telefonnummern für Audiokonferenzen in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md)
  
[Optionen für Onlinebesprechungen und Telefonkonferenzen festlegen](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
