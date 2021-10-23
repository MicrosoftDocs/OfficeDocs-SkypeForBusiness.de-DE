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
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Hier erfahren Sie, wie Sie Einwahl- oder Audiokonferenzen für Personen in Ihrem Unternehmen einrichten, die telefonisch an Konferenzanrufen teilnehmen müssen. '
ms.openlocfilehash: b61e03301f7d45cabd846c96097aee4cb971b635
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537026"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>Einrichten von Audiokonferenzen für Microsoft Teams

In einigen Fällen müssen Mitarbeiter in Ihrer Organisation sich über ein Telefon in eine Besprechung einwählen. Microsoft Teams bietet genau für solche Situationen das Audiokonferenz-Feature! Personen können sich in Teams-Besprechungen mit einem Telefon einwählen, anstatt die Microsoft Teams-App auf einem mobilen Gerät oder einem PC zu verwenden. 
  
You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Häufig gestellte Fragen zu Audiokonferenzen finden Sie unter [Häufig gestellte Fragen zu Audiokonferenzen](audio-conferencing-common-questions.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Schritt 1: Stellen Sie fest, ob Audiokonferenzen in Ihrem Land/Ihrer Region verfügbar sind
<a name="__top"> </a>

Gehen Sie auf [Länder- und Regionenverfügbarkeit für Audiokonferenzen und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) und wählen Sie Ihr Land oder Ihre Region aus, um Verfügbarkeitsinformationen über Audiokonferenzen sowie Informationen über Telefonanlage, Anrufpläne, gebührenfreie Nummern und Guthaben für Kommunikationen zu erhalten. 
 
## <a name="step-2-get-and-assign-licenses"></a>Schritt 2: Abrufen und Zuweisen von Lizenzen
 
1. Für Audiokonferenzen benötigen Sie eine Lizenz für jeden Benutzer, der Einwahlbesprechungen einrichtet. Informationen dazu, welche Lizenzen Sie für Audiokonferenzen erwerben müssen und was diese kosten, erhalten Sie unter [Add-On-Lizenzierung für Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

    >[!NOTE] 
    > Audiokonferenzen sind in Office 365 Enterprise E5-Lizenzen und als Add-On enthalten.
        
2. Nachdem Sie die Audiokonferenz-Lizenzen erworben haben, müssen Sie diese den Personen in Ihrer Organisation zuweisen, die Besprechungen planen oder leiten werden. Lesen Sie dazu [Zuweisen von Lizenzen an Benutzer in Microsoft 365 oder Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc). Dies gilt für Lizenzen, die Sie für die Personen in Ihrer Organisation erworben haben, die Besprechungen planen oder leiten werden.
    
3. Wir empfehlen auch, dass Sie Guthaben für Kommunikations-Lizenzen (sie kosten nichts) denselben Personen zuweisen, denen Sie im vorherigen Schritt Lizenzen zugewiesen haben. Weitere Informationen zum Guthaben für Kommunikationen finden Sie unter [Einrichten von Guthaben für Kommunikationen für Ihr Unternehmen](set-up-communications-credits-for-your-organization.md).
    
   > [!NOTE]
   > Sie können auch [Audiokonferenzen mit Minutenabrechnung](audio-conferencing-pay-per-minute.md) einrichten.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Schritt 3: Servicenummern für Ihre Konferenzbrücken anfordern
<a name="__top"> </a>

Für Audiokonferenzen können Sie keine Benutzertelefonnummern verwenden; Sie müssen Servicenummern anfordern. Sie können für Ihre Konferenzbrücken gebührenpflichtige oder gebührenfreie Servicenummern abrufen. Es gibt drei Möglichkeiten, gebührenpflichtige und gebührenfreie Servicenummern zu erhalten:
  
- **Über das Microsoft Teams Admin Center**. Für einige Länder/Regionen können Sie Servicenummern für Ihre Konferenzbrücken über das Microsoft Teams Admin Center erhalten. Siehe [Abrufen von Servicetelefonnummern](./getting-service-phone-numbers.md).
    
- **Portieren von bestehenden Servicenummern**. Portieren oder übertragen Sie vorhandene Telefonnummern von Ihrem derzeitigen Dienstanbieter oder Netzbetreiber zu Microsoft 365 oder Office 365. Über [Übertragen von Telefonnummern zu Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) oder [Rufnummern für Ihre Organisation verwalten](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) erhalten Sie weitere hilfreiche Informationen.  
  
- **Verwenden eines Anforderungsformulars für neue Telefonnummern**. Manchmal können Sie (je nach Land/Region) Ihre neuen Servicenummern nicht über das Microsoft Teams Admin Center beziehen, oder Sie benötigen bestimmte Telefonnummern oder Ortsvorwahlen. Wenn dies der Fall ist, müssen Sie ein Formular herunterladen und an uns zurücksenden. Weitere Informationen finden Sie unter [Verwalten von Rufnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Schritt 4: Zuweisen einer Servicenummer zur Konferenzbrücke
<a name="__top"> </a>

Sobald Sie Ihre gebührenpflichtigen und/oder gebührenfreien Telefonnummern für Ihre Konferenzbrücke erhalten, müssen Sie die Nummern zuweisen, damit sie für die Einladungen zu den Besprechungen verwendet werden können.  

Führen Sie die folgenden Schritte aus, um Ihrer Audiokonferenzbrücke eine neue Rufnummer zuzuweisen:

 **Verwenden des Microsoft Teams Admin Centers:**

 1. Wechseln Sie von Start zu  >  **Sprachanrufnummern Telefon**.
 2. Wählen Sie die entsprechende Telefonnummer aus, und klicken Sie auf **Zuweisen**.

Weitere Informationen finden Sie unter [Ändern der Telefonnummern Ihrer Audiokonferenzbrücke](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Schritt 5: Legen Sie die Standard- und Alternativsprachen für eine Konferenzbrücke fest
<a name="__top"> </a> Als Nächstes sollten Sie die [Sprachen für die automatische Telefonzentrale für Audiokonferenzen in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) festlegen, die die automatische Telefonkonferenzzentrale verwendet, um einen Anrufer zu begrüßen, wenn er sich mit einer Telefonnummer für Audiokonferenzen einwählt. 

 **Verwenden des Microsoft Teams Admin Centers:**

1. Wechseln Sie von Start zu **Besprechungen**  >  **Konferenzbrücken**.
2. Wählen Sie die Telefonnummer der Konferenzbrücke, klicken Sie auf **Bearbeiten**, und wählen Sie dann die Standardsprache aus.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Schritt 6: Servicenummern für Ihre Konferenzbrücken einstellen
<a name="__top"> </a>
    
Nachdem Sie Ihre Konferenzbrücke eingerichtet haben, vergewissern Sie sich, dass die Standardeinstellungen, wie z. B. Ein-/Ausgangsbenachrichtigungen und PIN-Länge, die sind, die Sie verwenden möchten; wenn nicht, können Sie sie ändern. 

 **Verwenden des Microsoft Teams Admin Centers:**

1. Wechseln Sie von Start zu **Besprechungen**  >  **Konferenzbrücken**.
2. Wählen Sie **Brückeneinstellungen** aus. Der **Brücke**-Einstellungsbereich wird geöffnet. 

Weitere Informationen finden Sie unter [Einstellungen für eine Audiokonferenzbrücke ändern](change-the-settings-for-an-audio-conferencing-bridge.md).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Schritt 7: Zuweisen von Einwahlnummern für Benutzer, die Besprechungen leiten

Nachdem Sie eine Audiokonferenzbrücke erstellt haben, müssen Sie die gebührenpflichtigen und gebührenfreien Nummern für Ihre Benutzer festlegen.

Sie müssen dies für alle Personen in Ihrer Organisation tun, die Besprechungen leiten oder planen. 

 **Verwenden des Microsoft Teams Admin Centers:**

1. Klicken Sie auf der Startseite auf **Benutzer**, wählen Sie den Benutzer in der Liste aus, und wählen Sie **Bearbeiten aus.**
2. Klicken Sie neben **Audiokonferenzen** auf **Bearbeiten**, und wählen Sie dann im Bereich **Audiokonferenzen** eine Nummer aus den Listen der **gebührenpflichtigen** und **gebührenfreien** Telefonnummern aus.

Weitere Informationen finden Sie unter [Zuweisen von Microsoft als Anbieter von Audiokonferenzen](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Schritt 8: Besprechungseinladungen einrichten (optional)
<a name="__top"> </a>
 
Die für den Nutzer festgelegten Einwahlnummern werden automatisch den Besprechungseinladungen hinzugefügt, die Besprechungsteilnehmern zugesendet werden. Sie können jedoch Ihre eigenen Hilfe- und rechtliche Links, eine SMS und eine kleine Firmengrafik hinzufügen, wenn Sie möchten. Siehe [Anpassen von Besprechungseinladungen](meeting-settings-in-teams.md#customize-meeting-invitations).
   
## <a name="related-topics"></a>Verwandte Themen

[Allgemeine Fragen zu Audiokonferenzen](audio-conferencing-common-questions.md)
  
[Telefonnummern für Audiokonferenzen in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md)
  
[Festlegen von Optionen für Onlinebesprechungen und Telefonkonferenzen](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
