---
title: Konfigurieren von Konten für Microsoft Teams-Räume
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
description: In diesem Thema erfahren Sie mehr über das Konfigurieren von Konten für Microsoft Teams-Räume in Exchange und Skype for Business.
ms.openlocfilehash: d66e495fd4e1e75227b162974891cda9876fef28c9f809dead001af1a95b099a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54348800"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Konfigurieren von Konten für Microsoft Teams-Räume
 
In diesem Thema erfahren Sie mehr über Microsoft Teams-Räume und die Integration in Exchange und Skype for Business.
  
In diesem Thema wird das Erstellen von Konten beschrieben, die von Microsoft Teams-Räume in Microsoft Exchange und Skype for Business. Bereitstellungsanweisungen für Microsoft Teams-Räume-Geräte finden Sie unter [Konfigurieren einer Microsoft Teams-Räume-Konsole.](console.md) Ihre Infrastruktur weist wahrscheinlich eine der folgenden Konfigurationen auf:
  
- Onlinebereitstellung: Die Umgebung Ihrer Organisation wird vollständig auf Microsoft 365 Oder Office 365. Weitere Informationen finden Sie unter [Bereitstellen Microsoft Teams-Räume mit Microsoft 365 oder Office 365.](with-office-365.md)
    
- Lokale Bereitstellung: Ihre Organisation verfügt über Server, die von ihr kontrolliert werden und auf denen Active Directory-, Exchange- Skype for Business Server gehostet werden. Weitere Informationen finden Sie unter Bereitstellen [Microsoft Teams-Räume mit Skype for Business Server](with-skype-for-business-server-2015.md)
    
- Hybridbereitstellungen: Ihre Organisation verfügt über eine Mischung von Diensten, von den einige lokal gehostet werden und einige online über Microsoft 365 oder Office 365. Im Microsoft Teams-Räume werden die folgenden Hybridszenarien unterstützt:
    
  - Exchange Online mit Skype for Business Server lokal. Weitere Informationen finden Sie unter [Bereitstellen Microsoft Teams-Räume mit Exchange Online (Hybrid).](with-exchange-online.md)
    
  - Exchange lokal mit Microsoft Teams oder Skype for Business Online. Weitere Informationen finden Sie unter [Bereitstellen Microsoft Teams-Räume mit Exchange lokal (Hybrid).](with-exchange-on-premises.md)
    
Ihre vorhandene Konfiguration beeinflusst die Vorbereitung der Geräteinstallation.
  
Microsoft Teams-Räume muss ein "Gerätekonto" in Active Directory, Exchange und Skype for Business. Das Konto wird verwendet, um auf seinen Besprechungskalender zu zugreifen und eine Microsoft Teams oder Skype for Business herstellen. Benutzer können dieses Konto buchen, indem sie eine Besprechung mit ihm planen. Microsoft Teams-Räume können an dieser Besprechung teilnehmen und den Besprechungsteilnehmern verschiedene Funktionen zur Verfügung stellen.
  
> [!IMPORTANT]
> Ohne ein Gerätekonto funktioniert keine dieser Features. 
  
Jedes Gerätekonto ist für ein einzelnes Microsoft Teams-Räume Gerät eindeutig und erfordert ein Setup:
  
- Das Gerätekonto muss ordnungsgemäß konfiguriert sein.
    
- Ihre Infrastruktur muss so konfiguriert werden, dass Microsoft Teams-Räume das Gerätekonto überprüfen und die entsprechenden Geräte Microsoft-Dienste.
    
> [!IMPORTANT]
> Es wird dringend empfohlen, das Konto rechtzeitig vor der eigentlichen Hardwareinstallation zu erstellen. Im Idealfall beginnen Sie zwei bis drei Wochen vor der Installation mit der Kontovorbereitung. 

In Hybridumgebungen muss für das für Microsoft Teams-Räume verwendete Konto die Kennwortsynchronisierung in der Azure Active Directory-Synchronisierung (AAD) aktiviert sein, da für die Microsoft Teams-Räume-Authentifizierung eine Microsoft 365 oder Office 365 erforderlich ist. Stellen Sie beim Einrichten des Kontos sicher, dass die SIP-Adresse des Kontos dem Benutzerprinzipalnamen (User Principal Name, UPN) in AAD entspricht. 
  
Sie können sich ein Gerätekonto als Ressourcenkonto auskennen, das von anderen Personen als Konto eines Konferenzraums oder Besprechungsraums erkannt wird. Wenn Sie eine Besprechung in diesem Konferenzraum planen möchten, laden Sie das Konto zu dieser Besprechung ein. Um die Microsoft Teams-Räume zu verwenden, gehen Sie genauso mit dem Gerätekonto vor, das jedem Konto zugewiesen ist.
  
Wenn Sie bereits ein Ressourcenpostfachkonto für den Besprechungsraum eingerichtet haben, in dem Sie Microsoft Teams-Räume installieren, können Sie dieses Ressourcenkonto in ein Gerätekonto ändern. Sobald dies erfolgt ist, müssen Sie nur noch das Gerätekonto zu einem Microsoft Teams-Räume hinzufügen. Siehe die nachstehenden Beispiele für die Einrichtung von Gerätekonton.
  
Mit einer zusätzlichen Konfiguration ist die Remoteverwaltung mithilfe des Microsoft Azure-Monitors möglich, wie unter Planen der Microsoft Teams-Räume-Verwaltung mit [Azure Monitor,](azure-monitor-plan.md)Bereitstellen der Microsoft Teams-Räume-Verwaltung mit [Azure Monitor](azure-monitor-deploy.md)und Verwalten von [Microsoft Teams-Räume-Geräten](azure-monitor-manage.md)mit Azure Monitor beschrieben. 
  
## <a name="basic-configuration"></a>Grundlegende Konfiguration

Diese Eigenschaften stellen die Mindestkonfiguration für ein Gerätekonto dar, mit dem sie Microsoft Teams-Räume. Ihr Gerätekonto erfordert möglicherweise eine weitere Einrichtung.
  
|**Eigenschaft**|**Zweck**|
|:-----|:-----|
|Exchange Postfach (Exchange 2013 SP1 oder höher oder Exchange Online)  <br/> |Wenn Sie das Konto mit einem Exchange-Postfach aktivieren, kann das Gerätekonto sowohl E-Mail- als auch Besprechungsanfragen empfangen und senden sowie einen Besprechungskalender auf dem Microsoft Teams-Räume anzeigen. Das Microsoft Teams-Räume Postfach muss ein Raumpostfach sein.  <br/> |
|Skype for Business ist aktiviert  <br/> |Skype for Business müssen aktiviert sein, um verschiedene Konferenzfunktionen wie Videoanrufe, Videoanrufe und Bildschirmfreigaben nutzen zu können. Sowohl Skype for Business Online als Skype for Business Server werden unterstützt.  <br/> |
|Kennwort aktiviert  <br/> |Das Gerätekonto muss mit einem Kennwort aktiviert werden, oder es kann sich nicht mit einem Exchange oder Skype for Business Server.  <br/> |
   
## <a name="advanced-configuration"></a>Erweiterte Konfiguration

Die Eigenschaften für die Grundlegende Konfiguration ermöglichen zwar die Einrichtung des Gerätekontos in einer einfachen Umgebung, es ist jedoch möglich, dass in Ihrer Umgebung weitere Einschränkungen hinsichtlich Verzeichniskonten gelten, die erfüllt werden müssen, damit Microsoft Teams-Räume das Gerätekonto erfolgreich verwenden kann.
  
|**Eigenschaft**|**Zweck**|
|:-----|:-----|
|Zertifikatbasierte Authentifizierung  <br/> |Zertifikate sind möglicherweise sowohl für Exchange als Skype for Business Server. Zum Bereitstellen von Zertifikaten können Sie diese laden, wenn Sie als Administrator angemeldet sind.  <br/> |
   
Die einfachste Möglichkeit zum Einrichten von Gerätekonten besteht in der Konfiguration der Konten mithilfe von Remotecomputern Windows PowerShell. Microsoft stellt [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)- ein Skript zur Unterstützung beim Erstellen neuer Gerätekonten oder zum Überprüfen vorhandener Ressourcenkonten zur Verwendung in kompatible Microsoft Teams-Räume-Gerätekonten zur Microsoft Teams-Räume zur Verwendung.
  
Wenn Sie die Benutzeroberfläche für Microsoft 365 oder Office 365-Cmdlets lieber Windows PowerShell verwenden möchten, können einige Schritte manuell ausgeführt werden. Siehe [Erstellen eines Gerätekontos mit Microsoft 365 oder Office 365.](/surface-hub/create-a-device-account-using-office-365)
  
## <a name="see-also"></a>Mehr dazu

[Plan für Microsoft Teams-Räume](rooms-plan.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)