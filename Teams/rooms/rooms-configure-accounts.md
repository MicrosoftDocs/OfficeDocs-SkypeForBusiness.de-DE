---
title: Konfigurieren von Konten für Microsoft Teams-Räume
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: In diesem Thema erfahren Sie mehr über das Konfigurieren von Konten für Microsoft Teams-Räume in Exchange und Skype for Business.
ms.openlocfilehash: 9c898d63291d6b2d4a8d2557f2e307156b3487b4
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503492"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Konfigurieren von Konten für Microsoft Teams-Räume
 
In diesem Thema erfahren Sie mehr über Microsoft Teams-Räume und die Integration in Exchange und Skype for Business.
  
In diesem Thema wird das Erstellen von Konten beschrieben, die von Microsoft Teams-Räume in Microsoft Exchange und Skype for Business. Ihre Infrastruktur weist wahrscheinlich eine der folgenden Konfigurationen auf:
  
- Onlinebereitstellung: Die Umgebung Ihrer Organisation wird ausschließlich nach Microsoft 365 Oder Office 365. Weitere Informationen finden Sie unter [Bereitstellen Microsoft Teams-Räume mit Microsoft 365 oder Office 365](with-office-365.md).
    
- Lokale Bereitstellung: Ihre Organisation verfügt über Server, die von ihr kontrolliert werden, wo Active Directory, Exchange und Skype for Business Server gehostet werden. Weitere Informationen finden Sie unter [Bereitstellen Microsoft Teams-Räume mit Skype for Business Server](with-skype-for-business-server-2015.md)
    
- Hybridbereitstellungen: Ihre Organisation verfügt über eine Mischung aus Diensten, von den einige lokal gehostet werden und einige online über Microsoft 365 oder Office 365. Im Microsoft Teams-Räume werden die folgenden Hybridszenarien unterstützt:
    
  - Exchange Online mit Skype for Business Server lokal. Weitere Informationen finden Sie unter [Bereitstellen Microsoft Teams-Räume mit Exchange Online (Hybrid).](with-exchange-online.md)
    
  - Exchange lokal mit Microsoft Teams. Weitere Informationen finden Sie unter [Bereitstellen Microsoft Teams-Räume mit Exchange lokal (Hybrid).](with-exchange-on-premises.md)
    
Ihre vorhandene Konfiguration beeinflusst die Vorbereitung der Geräteinstallation.
  
Microsoft Teams-Räume muss ein "Ressourcenkonto" in Active Directory, Exchange Und Skype for Business. Das Konto wird verwendet, um auf seinen Besprechungskalender zu zugreifen und eine Microsoft Teams oder Skype for Business herstellen. Benutzer können dieses Konto buchen, indem sie eine Besprechung mit ihm planen. Microsoft Teams-Räume können an dieser Besprechung teilnehmen und den Besprechungsteilnehmern verschiedene Funktionen zur Verfügung stellen.
  
> [!IMPORTANT]
> Ohne ein Ressourcenkonto funktioniert keine dieser Features. 
  
Jedes Ressourcenkonto ist für eine einzelne Microsoft Teams-Räume-Installation eindeutig und erfordert eine gewisse Einrichtung:
  
- Das Ressourcenkonto muss ordnungsgemäß konfiguriert sein.
    
- Ihre Infrastruktur muss so konfiguriert werden, Microsoft Teams-Räume Benutzer das Überprüfen des Ressourcenkontos und das Erreichen des entsprechenden Ressourcenkontos Microsoft-Dienste.

> [!NOTE] 
> Wenn Sie Microsoft Teams-Panels verwenden, meldet Teams-Räume-Ressourcenkonto sich sowohl bei den Teams-Räume als auch den zugeordneten Teams an.
    
> [!IMPORTANT]
> Es wird dringend empfohlen, das Konto rechtzeitig vor der eigentlichen Hardwareinstallation zu erstellen. Im Idealfall beginnen Sie zwei bis drei Wochen vor der Installation mit der Kontovorbereitung.
> 

In Hybridumgebungen muss für das für Microsoft Teams-Räume verwendete Konto die Kennwortsynchronisierung in Azure Active Directory (AAD) Sync aktiviert sein, da die Microsoft Teams-Räume-Authentifizierung eine Microsoft 365 oder eine Office 365  Authentifizierung. Stellen Sie beim Einrichten des Kontos sicher, dass die SIP-Adresse des Kontos mit dem Benutzerprinzipalnamen (User Principal Name, UPN) in der AAD. 
  
Sie können sich ein Ressourcenkonto als Ressourcenkonto auskennen, das von anderen Personen als Konto eines Konferenzraums oder eines gemeinsam genutzten Raums erkannt wird. Wenn Sie eine Besprechung an diesem Platz planen möchten, laden Sie das Konto zu dieser Besprechung ein.
  
Wenn Sie bereits ein Ressourcenpostfachkonto für den Speicherplatz eingerichtet haben, in dem Sie Microsoft Teams-Räume installieren, können Sie dieses Konto in ein Teams-Räume-Ressourcenkonto ändern. Sobald dies erfolgt ist, müssen Sie sich nur noch bei Microsoft Teams-Räume mit diesem Konto anmelden.
  
## <a name="basic-configuration"></a>Grundlegende Konfiguration

Diese Eigenschaften stellen die Mindestkonfiguration für ein Ressourcenkonto dar, mit dem sie Microsoft Teams-Räume. Ihr Ressourcenkonto erfordert möglicherweise eine weitere Einrichtung.
  
|**Eigenschaft**|**Zweck**|
|:-----|:-----|
|Exchange Postfach (Exchange 2013 SP1 oder höher oder Exchange Online)  <br/> |Durch Aktivieren des Kontos mit einem Exchange-Postfach kann das Ressourcenkonto sowohl E-Mail- als auch Besprechungsanfragen empfangen und senden sowie einen Besprechungskalender auf dem Microsoft Teams-Räume anzeigen. Das Microsoft Teams-Räume Postfach muss ein Raumpostfach sein.  <br/> |
|Skype for Business ist aktiviert  <br/> |Skype for Business können aktiviert werden, um verschiedene Skype for Business-Konferenzfeatures wie Videoanrufe, Videoanrufe und Bildschirmfreigaben zu verwenden.  <br/> |
|Kennwort aktiviert  <br/> |Das Ressourcenkonto muss mit einem Kennwort aktiviert werden, oder es kann sich nicht mit Microsoft Teams, Exchange oder Skype for Business Server. Der Kennwortablauf sollte für alle Teams-Räume deaktiviert werden.   <br/> |
   
## <a name="advanced-configuration"></a>Erweiterte Konfiguration

Die Eigenschaften für die Grundlegende Konfiguration ermöglichen zwar das Einrichten des Ressourcenkontos in einer einfachen Umgebung, es ist jedoch möglich, dass in Ihrer Umgebung weitere Einschränkungen für Verzeichniskonten gelten, die erfüllt werden müssen, damit Microsoft Teams-Räume das Ressourcenkonto erfolgreich verwenden kann.
  
|**Eigenschaft**|**Zweck**|
|:-----|:-----|
|Zertifikatbasierte Authentifizierung  <br/> |Zertifikate sind möglicherweise sowohl für Exchange als Skype for Business Server. Zum Bereitstellen von Zertifikaten können Sie diese laden, wenn Sie als Administrator angemeldet sind.  <br/> |
  
## <a name="see-also"></a>Mehr dazu

[Plan für Microsoft Teams-Räume](rooms-plan.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)
