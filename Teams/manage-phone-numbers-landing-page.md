---
title: Verwalten von Telefonnummern für Ihre Organisation
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davlick, roykuntz, jenstr
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
description: Erfahren Sie, wie Sie Telefonnummern von Benutzern (Abonnenten) und Diensten (gebührenpflichtige und gebührenfreie Telefonnummern) für Microsoft Teams für Ihre Organisation erhalten und verwalten.
ms.openlocfilehash: 613a3f5f287615c6e18024d1afba1d94d0fea67c
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606744"
---
# <a name="manage-telephone-numbers-for-your-organization"></a>Verwalten von Telefonnummern für Ihre Organisation

Derzeit unterstützt Microsoft zwei Telefonnummerntypen: 

- [**Benutzernummern**](#user-telephone-numbers), auch als Abonnentennummern bezeichnet, die Benutzern in Ihrer Organisation zugewiesen werden können.

- [**Servicenummern**](#service-telephone-numbers), die Diensten wie [Audiokonferenzen](deploy-audio-conferencing-teams-landing-page.md), [automatische Telefonzentralen](plan-auto-attendant-call-queue.md) oder [Anrufwarteschleifen](plan-auto-attendant-call-queue.md) zugewiesen sind.

Microsoft arbeitet an der Vereinfachung von Nummerntypen, aber vorerst müssen Sie folgendes entscheiden:

- Welche Benutzerstandorte benötigen neue Telefonnummern von Microsoft?
- Welche Art von Telefonnummer (Abonnenten oder Dienst) benötige ich?
- 如何实现 vorhandene Telefonnummern zu Teams portieren?

Wie Sie Telefonnummern erwerben und verwalten, hängt von ihrer PSTN-Konnektivitätsoption ab.

- Informationen zum Verwalten von Telefonnummern für Microsoft-Anrufpläne finden [Sie unter Verwalten von Telefonnummern für Anrufpläne](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Informationen zum Verwalten von Telefonnummern für Telefonieanbieter finden Sie unter [Einrichten von Telefonnummern mit Telefonieanbieter](operator-connect-configure.md#set-up-phone-numbers).

- Informationen zum Verwalten von Telefonnummern für Telefonieanbieter mit Mobil (Public Preview-Version) finden [Sie unter Einrichten von Telefonnummern mit Telefonieanbieter mit Mobil](operator-connect-mobile-configure.md#set-up-phone-numbers).

- Informationen zum Verwalten von Telefonnummern für Direct Routing finden Sie unter [Konfigurieren der Telefonnummer und Aktivieren von Enterprise-VoIP](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice).




> [!NOTE]
> Wenn Sie weitere oder andere Nummerntypen benötigen, die nicht im Microsoft Teams Admin Center angezeigt werden, können Sie eine Telefonnummernanforderung an das [Telefonnummern-Service Center](https://pstnsd.powerappsportals.com/) senden.

## <a name="user-telephone-numbers"></a>Telefonnummern des Benutzers

Es gibt zwei Arten von Benutzertelefonnummern, die Benutzern in Ihrer Organisation zugewiesen werden können:  
    
- **Geografische Nummern** haben eine Beziehung zu einem geografischen Gebiet und sind die am häufigsten verwendeten. Beispielsweise können geografische Telefonnummern in den meisten Fällen nur innerhalb einer bestimmten Adresse, einer bestimmten Stadt, eines Bundesstaats oder einer bestimmten Region des Landes verwendet werden.
    
- **Nicht geografische Nummern** werden als nationale Nummern oder manchmal Als VoIP-Nummern bezeichnet. Diese Zahlen haben keine Beziehung zu einem geografischen Gebiet innerhalb eines Landes/einer Region. Beispielsweise haben nicht geografische Nummern häufig die gleichen Kosten, wenn sie von überall innerhalb des Landes/der Region aus anzurufen sind. Außerdem stehen in einigen Ländern, z. B. Dänemark, nur nicht geografische Nummern zur Verfügung.


## <a name="service-telephone-numbers"></a>Servicetelefonnummern  

In diesem Abschnitt werden die von Microsoft verfügbaren Dienstnummern beschrieben, die in Ihrer Lizenzierung enthalten sind. Informationen zu Servicenummern, die von Operator Connect oder Direct Routing bereitgestellt werden, erhalten Sie von Ihrem Anbieter. 

Es gibt zwei Arten von Servicetelefonnummern, die von Microsoft bereitgestellt werden – gebührenpflichtige und gebührenfreie Telefonnummern, die Diensten wie Audiokonferenzen, automatische Telefonzentralen oder Anrufwarteschleifen zugewiesen werden können. Dienstnummern haben eine höhere Kapazität für gleichzeitige Anrufe als Benutzernummern. Die Verfügbarkeit von Servicenummern variiert je nach Land/Region und der Art der Nummer (unabhängig davon, ob es sich um eine gebührenpflichtige oder gebührenfreie Nummer handelt). Die Telefonielizenzen von Microsoft in jedem Land/jeder Region bestimmen, wofür die Nummer verwendet werden kann.
    
 - **Gebührenpflichtige Servicenummern** : Es gibt zwei Arten von gebührenpflichtigen Servicenummern, die dem Anrufer gebührenpflichtige Kosten verursachen können:
    
   - **Geografische Nummern** Geografische Nummern haben eine Beziehung zu einem geografischen Gebiet. Beispielsweise können geografische Telefonnummern in den meisten Fällen nur innerhalb einer bestimmten Adresse, einer bestimmten Stadt, eines Bundesstaats oder einer bestimmten Region des Landes verwendet werden.
        
   - **Nicht geografische Nummern** Nicht geografische Nummern sind nationale Nummern, die keine Beziehung zu einem geografischen Gebiet innerhalb eines Landes/einer Region haben. Beispielsweise haben nicht geografische Nummern häufig die gleichen Kosten, wenn sie von überall innerhalb des Landes/der Region aus anzurufen sind.
   
- **Gebührenfreie Servicenummern** – Diese Servicenummern verursachen normalerweise keine gebührenpflichtigen Kosten für den Anrufer. Teams stellt nationale gebührenfreie Telefonnummern in über 60 Ländern/Regionen bereit.
    
    > [!CAUTION]
    > Einige Länder/Regionen und Nummerntypen, z. B. Anrufe, die von Mobiltelefonen ausgehen, können in einigen Fällen gebührenpflichtige Kosten für den Anrufer verursachen. 

## <a name="where-phone-numbers-are-managed"></a>Wo Telefonnummern verwaltet werden

Wo und wie Nummern verwaltet werden, hängt von der PSTN-Konnektivitätsoption ab:

- Microsoft-Anrufplan und Telefonnummern für Telefonieanbieter können nur in Microsoft 365 verwaltet werden.

- Direct Routing-Telefonnummern können in der жергілікті Active Directory oder in Microsoft 365 verwaltet werden, wie in den folgenden Abschnitten beschrieben.

### <a name="direct-routing-numbers-managed-in-an-on-premises-active-directory"></a>In einem жергілікті Active Directory verwaltete Direct Routing-Nummern

Wenn Sie eine Skype for Business Server Hybridbereitstellung haben oder hatten, synchronisiert sich Ihr жергілікті Active Directory höchstwahrscheinlich mit Microsoft 365. Dies bedeutet, dass Verzeichnisattribute für Benutzer- und Ressourcenkonten in der жергілікті Active Directory verwaltet und mit Microsoft 365 synchronisiert werden.

Wenn die Direct Routing-Telefonnummer für das Benutzer- oder Ressourcenkonto im жергілікті Active Directory verwaltet wird, enthält der Parameter "msRTCSIP-Line" für das Konto einen Wert. Sie können ein Tool wie ADSI Edit verwenden, um den MsRTCSIP-Line-Parameter für ein Benutzer- oder Ressourcenkonto anzuzeigen, dem eine Direct Routing-Telefonnummer in жергілікті Active Directory zugewiesen ist.   

Nachdem dieser Parameter über den Verzeichnissynchronisierungsprozess (Azure AD Connect) automatisch mit dem Benutzer- oder Ressourcenkonto in Microsoft 365 synchronisiert wurde, können Sie die Telefonnummer anzeigen, indem Sie sich den OnPremLineURi-Parameter in der Ausgabe des [Cmdlets "Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) " ansehen.

| Wo | Parameter | Wert |
| :------------| :-------| :---------|
| Lokales AD | msRTCSIP-Line | tel:+14255551234 |
| Microsoft 365 | OnPremLineURi | tel:+14255551234 |

### <a name="direct-routing-numbers-managed-in-microsoft-365"></a>In Microsoft 365 verwaltete Direct Routing-Nummern

Wenn Sie keine Direct Routing-Telefonnummern in der жергілікті Active Directory verwalten, werden diese in Microsoft 365 verwaltet. Da die Telefonnummern nicht mit Microsoft 365 synchronisiert werden, sind sie im OnPremLineUri-Parameter in der Ausgabe des Get-CsOnlineUser Cmdlets, das für das Benutzer- oder Ressourcenkonto ausgeführt wird, nicht sichtbar.

### <a name="direct-routing-numbers-managed-in-both-an-on-premises-active-directory-and-microsoft-365"></a>Direct Routing-Nummern, die sowohl in einem жергілікті Active Directory als auch in Microsoft 365 verwaltet werden

Es ist möglich, Direct Routing-Telefonnummern einiger Benutzer- und Ressourcenkonten in einem жергілікті Active Directory und Direct Routing-Telefonnummern anderer Konten in Microsoft 365 zu verwalten. Diese Funktion hängt davon ab, ob das Attribut "msRTCSIP-Line" für das Benutzer- oder Ressourcenkonto im жергілікті Active Directory festgelegt ist.    

### <a name="change-where-direct-routing-phone-numbers-are-managed"></a>Ändern der Verwalteten Direct Routing-Telefonnummern

Um zu ändern, wo eine Direct Routing-Telefonnummer verwaltet wird, müssen Sie die Telefonnummer aus dem msRTCSIP-Line-Attribut des Benutzers entfernen oder das Konto im жергілікті Active Directory erneut angeben.   

Weitere Informationen finden Sie unter ["Skype for Business Attribute für alle lokalen Benutzer in Active Directory löschen](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory.md)". Beachten Sie, dass die Telefonnummer dem Benutzer- oder Ressourcenkonto in Microsoft 365 neu zugewiesen werden muss.

Nachdem das Entfernen mit Microsoft 365 synchronisiert wurde, ist das OnPremLineUri-Attribut in der Ausgabe von Get-CsOnlineUser für das Benutzer- oder Ressourcenkonto leer. 

