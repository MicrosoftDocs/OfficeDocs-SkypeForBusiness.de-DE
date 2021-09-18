---
title: Verwalten von Telefonnummern für Ihre Organisation
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
ms.topic: conceptual
ms.assetid: 6b61cb3c-361c-48a8-a9ef-d81bddde27bb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.overview
- ms.teamsadmincenter.voice.searchandacquire.PSTNpartner
- ms.lync.lac.NewNumberManualAcquisitionOpenSupportTicket
- ms.lync.lac.VASAMissingGeoCodes
- Calling Plans
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie Telefonnummern für Benutzer (Abonnent) und Dienste (gebührenpflichtige und gebührenfreie) Für Microsoft Teams Organisation erhalten und verwalten.
ms.openlocfilehash: d29781e16c881c9b0e00e39c6e57314c6696d8bb
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432796"
---
# <a name="manage-telephone-numbers-for-your-organization"></a>Verwalten von Telefonnummern für Ihre Organisation

Derzeit unterstützt Microsoft zwei Arten von Telefonnummern: 

- [**Benutzernummern**](#user-telephone-numbers), auch als Abonnentennummern bezeichnet, die Benutzern in Ihrer Organisation zugewiesen werden können.

- [**Servicenummern**](#service-telephone-numbers), die Diensten wie [Audiokonferenzen,](deploy-audio-conferencing-teams-landing-page.md) [automatischen](plan-auto-attendant-call-queue.md)Telefonkonferenzen oder [Anrufwarteschleifen zugewiesen sind.](plan-auto-attendant-call-queue.md)

Microsoft arbeitet an der Vereinfachung von Zahlentypen, doch vorerst müssen Sie sich entscheiden:

- An welchen Benutzerstandorten benötigen Sie neue Telefonnummern von Microsoft?
- Welche Art von Telefonnummer (Abonnent oder Dienst) brauche ich?
- Wie portiert ich vorhandene Telefonnummern zu Teams?

Die Art und Weise, wie Sie Telefonnummern erwerben und verwalten, hängt von der PstN-Konnektivitätsoption ab.

- Informationen zum Verwalten von Telefonnummern für den Microsoft-Anrufplan finden Sie unter [Verwalten von Telefonnummern für Anrufpläne.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- Informationen zum Verwalten von Telefonnummern für Verbinden Operatoren finden Sie unter Einrichten von [Telefonnummern mit Verbinden.](operator-connect-configure.md#set-up-phone-numbers)

- Informationen zum Verwalten von Telefonnummern für Direct Routing finden Sie unter Konfigurieren der Telefonnummer [und Aktivieren von Enterprise-Voicemail und -Voicemail.](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)

Wenn Sie zusätzliche oder andere Nummerntypen benötigen, die nicht mit den im Microsoft Teams Admin Center zu sehen sind, können Sie eine Telefonnummernanforderung an [das Telefon Number Service Center senden.](https://pstnsd.powerappsportals.com/)

## <a name="user-telephone-numbers"></a>Telefonnummern von Benutzern

Es gibt zwei Arten von Benutzertelefonnummern, die Benutzern in Ihrer Organisation zugewiesen werden können:  
    
- **Geografische Nummern** haben eine Beziehung zu einem geografischen Bereich und sind am häufigsten. Geografische Telefonnummern können z. B. in den meisten Fällen nur innerhalb einer bestimmten Adresse, einer bestimmten Stadt, einem Bundesland oder einer Region des Landes verwendet werden.
    
- **Nicht geografische Nummern werden** als Nationalnummern oder manchmal auch VoIP-Nummern bezeichnet. Diese Nummern haben keine Beziehung zu einem geografischen Bereich innerhalb eines Lands bzw. einer Region. Beispielsweise haben nicht geografische Nummern häufig die gleichen Kosten, wenn Sie die Nummer von einem beliebigen Ort innerhalb des Landes bzw. der Region aus anrufen. Außerdem sind in einigen Ländern, z. B. Dänemark, nur nicht geografische Nummern verfügbar.


## <a name="service-telephone-numbers"></a>Servicetelefonnummern  

In diesem Abschnitt werden die von Microsoft verfügbaren Leistungsnummern beschrieben, die in Ihrer Lizenzierung enthalten sind. Wenn Sie Informationen zu den von der Netzbetreiber-Verbinden oder Direct Routing bereitgestellten Leistungsnummern erhalten, wenden Sie sich an Ihren Anbieter. 

Es gibt zwei Arten von Servicetelefonnummern, die von Microsoft bereitgestellt werden: gebührenpflichtig und gebührenfrei, die Diensten wie Audiokonferenzen, automatischen Telefonkonferenzen oder Anrufwarteschleifen zugewiesen werden können. Leistungsnummern haben eine höhere Kapazität für gleichzeitige Anrufe als Benutzernummern. Die Verfügbarkeit von Servicenummer ist je nach Land/Region und Art der Nummer (gebührenpflichtige oder gebührenfreie Nummer) unterschiedlich. Die Telefonielizenzen von Microsoft in jedem Land/jeder Region bestimmen, wofür die Nummer verwendet werden kann.
    
 - **Gebührenpflichtige Leistungsnummern** – Es gibt zwei Arten von gebührenpflichtigen Leistungsnummern, die für den Anrufer zu gebührenpflichtigen Kosten werden können:
    
   - **Geografische Nummern** Geografische Nummern haben eine Beziehung zu einem geografischen Bereich. Geografische Telefonnummern können z. B. in den meisten Fällen nur innerhalb einer bestimmten Adresse, einer bestimmten Stadt, einem Bundesland oder einer Region des Landes verwendet werden.
        
   - **Nicht ortsfreie Nummern** Nicht geografische Nummern sind nationale Nummern, die keine Beziehung zu einem geografischen Bereich innerhalb eines Lands bzw. einer Region haben. Beispielsweise haben nicht geografische Nummern häufig die gleichen Kosten, wenn Sie die Nummer von einem beliebigen Ort innerhalb des Landes bzw. der Region aus anrufen.
   
- **Gebührenfreie Leistungsnummern** – Für diese Servicenummern entstehen dem Anrufer in der Regel keine gebührenpflichtigen Kosten. Teams stellt nationale, gebührenfreie Telefonnummern in mehr als 60 Ländern/Regionen zur Verfügung.
    
    > [!CAUTION]
    > Einige Länder/Regionen sowie Nummerntypen, z. B. Anrufe von Mobiltelefonen, können in einigen Fällen gebührenpflichtig für den Anrufer an fallen. 


    
  
> [!NOTE]
> Wenn Sie mehr als diese Telefonnummern benötigen, wenden Sie sich an das Telefon [Number Service Center.](https://pstnsd.powerappsportals.com/)