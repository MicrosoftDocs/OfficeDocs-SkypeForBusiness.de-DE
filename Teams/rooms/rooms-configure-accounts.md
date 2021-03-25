---
title: Konfigurieren von Konten für Microsoft Teams Rooms
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: In diesem Thema finden Sie Informationen zum Konfigurieren von Konten für Microsoft Teams Rooms in Exchange und Skype for Business.
ms.openlocfilehash: 26879b2c07b859e65255ed84bedd4897b75d5caa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117473"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Konfigurieren von Konten für Microsoft Teams Rooms
 
In diesem Thema erfahren Sie mehr über Microsoft Teams Rooms und die Integration in Exchange und Skype for Business.
  
In diesem Thema wird das Erstellen von Konten beschrieben, die von Microsoft Teams Rooms in Microsoft Exchange und Skype for Business verwendet werden. Bereitstellungsanweisungen für Microsoft Teams Rooms-Geräte finden Sie unter [Konfigurieren einer Microsoft Teams Rooms-Konsole.](console.md) Ihre Infrastruktur weist wahrscheinlich eine der folgenden Konfigurationen auf:
  
- Onlinebereitstellung: Die Umgebung Ihrer Organisation wird vollständig in Microsoft 365 oder Office 365 bereitgestellt. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams-Räumen mit Microsoft 365 oder Office 365.](with-office-365.md)
    
- Lokale Bereitstellung: Ihre Organisation verfügt über Server, die sie steuert, auf denen Active Directory, Exchange und Skype for Business Server gehostet werden. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams-Räumen mit Skype for Business Server.](with-skype-for-business-server-2015.md)
    
- Hybridbereitstellungen: Ihre Organisation verfügt über eine Kombination von Diensten, bei der einige lokal und einige über Microsoft 365 oder Office 365 online gehostet werden. Bei Microsoft Teams Rooms werden die folgenden Hybridszenarien unterstützt:
    
  - Exchange Online mit Skype for Business Server lokal. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams-Räumen mit Exchange Online (Hybrid).](with-exchange-online.md)
    
  - Exchange lokal mit Microsoft Teams oder Skype for Business Online. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams-Räumen mit Exchange lokal (Hybrid).](with-exchange-on-premises.md)
    
Ihre vorhandene Konfiguration beeinflusst die Vorbereitung der Geräteinstallation.
  
Microsoft Teams Rooms muss in Active Directory, Exchange und Skype for Business ein "Gerätekonto" zugewiesen werden. Das Konto wird verwendet, um auf seinen Besprechungskalender zu zugreifen und Microsoft Teams oder Skype for Business-Konnektivität zu schaffen. Benutzer können dieses Konto buchen, indem sie eine Besprechung mit ihm planen. Microsoft Teams Rooms kann an dieser Besprechung teilnehmen und den Besprechungsteilnehmern verschiedene Features bereitstellen.
  
> [!IMPORTANT]
> Ohne Gerätekonto funktioniert keines dieser Features. 
  
Jedes Gerätekonto ist für ein einzelnes Microsoft Teams Rooms-Gerät eindeutig und erfordert einige Setups:
  
- Das Gerätekonto muss ordnungsgemäß konfiguriert sein.
    
- Ihre Infrastruktur muss so konfiguriert sein, dass Microsoft Teams Rooms das Gerätekonto überprüfen und die entsprechenden Microsoft-Dienste erreichen kann.
    
> [!IMPORTANT]
> Es wird dringend empfohlen, das Konto rechtzeitig vor der eigentlichen Hardwareinstallation zu erstellen. Im Idealfall beginnen Sie zwei bis drei Wochen vor der Installation mit der Kontovorbereitung. 

In Hybridumgebungen muss für das für Microsoft Teams Rooms verwendete Konto die Kennwortsynchronisierung in Azure Active Directory (AAD) Sync aktiviert sein, da für die Microsoft Teams Rooms-Authentifizierung Microsoft 365- oder Office 365-Authentifizierung erforderlich ist. Stellen Sie beim Einrichten des Kontos sicher, dass die SIP-Adresse des Kontos dem Benutzerprinzipalnamen (User Principal Name, UPN) in AAD entspricht. 
  
Sie können ein Gerätekonto als Ressourcenkonto sehen, das personen als Konto eines Konferenzraums oder Besprechungsraums erkennen. Wenn Sie eine Besprechung in diesem Konferenzraum planen möchten, laden Sie das Konto zu dieser Besprechung ein. Um Microsoft Teams Rooms am wirkungsvollsten zu verwenden, müssen Sie dasselbe mit dem Gerätekonto tun, das jedem Gerät zugewiesen ist.
  
Wenn Sie bereits ein Ressourcenpostfachkonto für den Besprechungsraum eingerichtet haben, in dem Sie Microsoft Teams Rooms installieren, können Sie dieses Ressourcenkonto in ein Gerätekonto ändern. Sobald sie fertig sind, müssen Sie nur noch das Gerätekonto zu einem Microsoft Teams Rooms-Gerät hinzufügen. Weitere Informationen finden Sie unten unter Setupbeispiele für Gerätekonto.
  
Bei zusätzlicher Konfiguration ist die Remoteverwaltung mithilfe von Microsoft Azure Monitor möglich, wie unter Planen der Verwaltung von Microsoft Teams-Räumen mit [Azure Monitor,](azure-monitor-plan.md)Bereitstellen der Verwaltung von [Microsoft Teams-Räumen](azure-monitor-deploy.md)mit Azure Monitor und Verwalten [von Microsoft Teams Rooms-Geräten](azure-monitor-manage.md)mit Azure Monitor beschrieben. 
  
## <a name="basic-configuration"></a>Grundlegende Konfiguration

Diese Eigenschaften stellen die Mindestkonfiguration für ein Gerätekonto dar, um mit Microsoft Teams Rooms arbeiten zu können. Ihr Gerätekonto erfordert möglicherweise eine weitere Einrichtung.
  
|**Eigenschaft**|**Zweck**|
|:-----|:-----|
|Exchange-Postfach (Exchange 2013 SP1 oder höher oder Exchange Online)  <br/> |Wenn Sie das Konto mit einem Exchange-Postfach aktivieren, bietet das Gerätekonto die Möglichkeit, E-Mail- und Besprechungsanfragen zu empfangen und zu senden sowie einen Besprechungskalender auf dem Microsoft Teams Rooms-Gerät anzuzeigen. Das Microsoft Teams Rooms-Postfach muss ein Raumpostfach sein.  <br/> |
|Skype for Business ist aktiviert  <br/> |Skype for Business muss aktiviert sein, damit verschiedene Konferenzfunktionen wie Videoanrufe, Chats und Bildschirmfreigaben verwendet werden können. Sowohl Skype for Business Online als auch Skype for Business Server werden unterstützt.  <br/> |
|Kennwort aktiviert  <br/> |Das Gerätekonto muss mit einem Kennwort aktiviert sein, oder es kann sich weder bei Exchange noch bei Skype for Business Server authentifizieren.  <br/> |
   
## <a name="advanced-configuration"></a>Erweiterte Konfiguration

Die Eigenschaften für die grundlegende Konfiguration ermöglichen zwar die Einrichtung des Gerätekontos in einer einfachen Umgebung, doch ist es möglich, dass Ihre Umgebung andere Einschränkungen für Verzeichniskonten hat, die erfüllt werden müssen, damit Microsoft Teams Rooms das Gerätekonto erfolgreich verwenden kann.
  
|**Eigenschaft**|**Zweck**|
|:-----|:-----|
|Zertifikatbasierte Authentifizierung  <br/> |Möglicherweise sind Zertifikate für Exchange und Skype for Business Server erforderlich. Zum Bereitstellen von Zertifikaten können Sie diese laden, wenn Sie als Administrator angemeldet sind.  <br/> |
   
Die einfachste Möglichkeit zum Einrichten von Gerätekonten besteht in der Konfiguration mithilfe von Remotekonten Windows PowerShell. Microsoft stellt [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)zur Verfügung, ein Skript, das beim Erstellen neuer Gerätekonten hilft, oder vorhandene Ressourcenkonten zu überprüfen, über die Sie verfügen, um sie in kompatible Microsoft Teams Rooms-Gerätekonten zu verwandeln.
  
Wenn Sie die Microsoft 365- oder Office 365-UI lieber über Windows PowerShell verwenden möchten, können einige Schritte manuell ausgeführt werden. Weitere Informationen finden Sie unter Erstellen [eines Gerätekontos mit Microsoft 365 oder Office 365.](/surface-hub/create-a-device-account-using-office-365)
  
## <a name="see-also"></a>Mehr dazu

[Plan für Microsoft Teams-Räume](rooms-plan.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)