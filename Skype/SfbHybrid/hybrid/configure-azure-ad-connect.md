---
title: Konfigurieren von Azure AD Connect
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Anweisungen zum Konfigurieren von Azure AD Connect in einer Hybridumgebung.
ms.openlocfilehash: 5095f3b22dfe3f4dcbfd2a0e3296794b80433b82
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119014"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Konfigurieren von Azure AD Connect für Teams und Skype for Business
 
Organisationen, die über lokale Skype for Business Server (oder Lync Server) verfügen und entweder Teams oder Skype for Business Online verwenden möchten, müssen Azure AD Connect konfigurieren, um ihr lokales Verzeichnis mit Microsoft 365 oder Office 365 zu synchronisieren, wie in diesem Dokument beschrieben.  Dazu gehören Organisationen, die direkt von Skype for Business lokal zu Teams wechseln. Insbesondere müssen Organisationen mit lokalem Skype for Business sicherstellen, dass die richtigen msRTCSIP-Attribute in Azure AD synchronisiert werden. 

> [!NOTE]
> Bestehende Teams Benutzer, die Skype for Business auch lokal haben, müssen ihr Konto für das lokale Skype for Business in die Cloud verschieben, um die vollständige Funktionalität zu erhalten, z. B. die Möglichkeit, mit Skype for Business-Benutzern zusammen zu arbeiten und mit Benutzer in Verbundorganisationen zu kommunizieren. Auch wenn der Benutzer nur Teams verwendet, wird dieses Skype for Business-Konto für die Infrastruktur benötigt, um die zusätzlichen Funktionen bereitzustellen.  Damit diese Migration durchgeführt werden kann, müssen Sie sicherstellen, dass Azure AD Connect ordnungsgemäß konfiguriert ist, damit Sie Hybrid aktivieren können.
 

## <a name="background-information"></a>Hintergrundinformationen

Azure Active Directory Connect sorgt dafür, dass Ihr lokales Active Directory kontinuierlich mit Microsoft 365 oder Office 365 synchronisiert wird.  Ihr lokales Verzeichnis bleibt die autorisierende Identitätsquelle, und Änderungen in Ihrer lokalen Umgebung werden in Azure AD synchronisiert. Weitere Informationen finden Sie unter [Azure AD Connect Sync](/azure/active-directory/hybrid/how-to-connect-sync-whatis).  Auch wenn Sie nicht alle Benutzer von der lokalen in die Cloud verschieben, müssen alle Benutzer, die Teams, Skype for Business lokal oder Skype for Business Online verwenden, von lokal in Azure AD synchronisiert werden, um die Kommunikation zwischen lokalen und Onlinebenutzern sicherzustellen. *Benutzer in Ihrer Organisation werden sowohl in den lokalen als auch in den Onlineverzeichnissen dargestellt.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Konfigurieren von Azure AD, wenn Sie Skype for Business Server haben 

Unabhängig davon, ob Sie über eine lokale Active Directory-Gesamtstruktur oder mehrere Gesamtstrukturen verfügen, kann Azure AD Connect in einer Vielzahl von unterstützten Topologien verwendet werden, wie unter [Topologien für Azure AD Connect beschrieben.](/azure/active-directory/hybrid/plan-connect-topologies)  Im Hinblick auf Skype for Business Server gibt es drei Hauptvarianten: 

1. Eine einzelne Gesamtstruktur, die autorisierende Benutzeridentitäten enthält und Skype for Business Server hostet. 

2. Mehrere Gesamtstrukturen, von denen jeweils nur eine Skype for Business Server hostet, sowie eine oder mehrere andere Gesamtstrukturen, die autorisierende Benutzeridentitäten (die Kontogesamtstrukturen) enthalten. 

3. Mehrere Bereitstellungen von Skype for Business Server in mehreren Gesamtstrukturen. Sofern bestimmte Anforderungen erfüllt sind, können Organisationen diese mehreren Bereitstellungen in einer einzigen Microsoft 365- oder Office 365-Organisation konsolidieren.

### <a name="single-forest"></a>Einzelne Gesamtstruktur 

Wenn Benutzerkonten und Skype for Business in einer einzigen Gesamtstruktur gehostet werden, müssen Sie sicherstellen, dass Azure AD Connect so konfiguriert ist, dass Benutzer aus dieser Gesamtstruktur mit Azure AD synchronisiert werden.  Der Installations-Assistent für Azure AD Connect bietet zwar eine Vielzahl von Optionen, die entsprechenden Attribute werden aber automatisch in Azure Active Directory synchronisiert. Kunden wird davon abgeraten, die integrierten Synchronisierungsregeln und/oder Connectors zu ändern, die die Konfiguration verwalten (was nicht über den Installationsassistenten möglich ist).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Mehrere Gesamtstrukturen mit einer Skype for Business-Bereitstellung 

Dieses Szenario wird häufig als eine Topologie mit Ressourcengesamtstruktur bezeichnet. Die autorisierenden Identitäten der Benutzer werden in einer oder mehreren Kontengesamtstrukturen gehostet, und Skype for Business wird in einer separaten Ressourcengesamtstruktur bereitgestellt (die ihrerseits ggf. auch autorisierende Benutzeridentitäten hostet). Im Allgemeinen können sich die autorisierenden Identitäten für Skype for Business-Benutzer in der gleichen Gesamtstruktur wie Skype for Business Server und/oder in einer anderen Gesamtstruktur befinden, vorausgesetzt: 

- Benutzer, die autorisierende Identitäten aus den Kontengesamtstrukturen aufweisen, werden in der Ressourcengesamtstruktur (in der der Skype for Business-Server bereitgestellt wird) als deaktivierte Benutzerobjekte dargestellt, und das Attribut "msRTCSIP-OriginatorSID" in der Ressourcengesamtstruktur stimmt mit der SID in der Kontengesamtstruktur überein. Weitere Informationen finden Sie [unter Configure a multi-forest environment for hybrid Skype for Business](configure-a-multi-forest-environment-for-hybrid.md).

- Die Ressourcengesamtstruktur, die Skype for Business Server hostet, vertraut den Kontengesamtstrukturen.  

- Alle relevanten Benutzerobjekte und Attribute für die Identität (aus der Kontengesamtstruktur) und Skype for Business (aus der Ressourcengesamtstruktur) werden mit Azure AD mit den korrekten Werten über Azure AD Connect synchronisiert.  

 Um eine ordnungsgemäße Objekt- und Attributsynchronisierung in Azure AD in einem lokalen Szenario mit mehreren Gesamtstrukturen zu [erreichen,](configure-a-multi-forest-environment-for-hybrid.md)empfiehlt Microsoft dringend die Verwendung von Azure AD Connect zum Synchronisieren aus allen Gesamtstrukturen mit aktivierten Benutzerkonten und der Gesamtstruktur, die Skype for Business enthält.  Wenn Sie aus allen Gesamtstrukturen synchronisieren, müssen Sie Azure AD Connect so konfigurieren, dass diese Identitäten zusammengeführt und mit Azure AD synchronisiert werden. Azure AD Connect dient zur Behandlung dieses Szenarios und bietet eine integrierte Option im Installations-Assistenten, um dies einzurichten, einschließlich Anker zum Verknüpfen von Identitäten.  Wählen Sie Folgendes aus: Benutzeridentitäten sind in mehreren Verzeichnissen vorhanden. Übereinstimmung mit --> ObjectSID- und msExchangeMasterAccountSID-Attributen.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Mehrere Bereitstellungen von Skype for Business Server in mehreren Gesamtstrukturen 

In diesem Szenario gibt es mehrere Gesamtstrukturen, die jeweils Skype for Business Server enthalten, und eine einzelne Microsoft 365- oder Office 365-Organisation.  Jede Gesamtstruktur, die Skype for Business Server enthält, kann mithilfe von AAD Connect in Azure AD für diese Organisation synchronisiert werden. Es kann immer nur höchstens eine Gesamtstruktur für die Skype for Business-Hybridbereitstellung konfiguriert werden. Vor dem Aktivieren der Hybridbereitstellung in einer Gesamtstruktur müssen alle SIP-Domänen aus allen anderen Gesamtstrukturen mithilfe von [disable-csonlineSipDomain deaktiviert werden.](/powershell/module/skype/disable-csonlinesipdomain) Weitere Informationen zum Konsolidieren einer solchen Umgebung in Microsoft 365 oder Office 365 finden Sie unter [Cloudkonsolidierung für Teams und Skype for Business](cloud-consolidation.md).

## <a name="general-requirements"></a>Allgemeine Anforderungen 

Sowohl die Teams- als auch die Skype for Business Online-Dienste erfordern, dass die richtigen Active Directory-Attribute vorhanden sind und in Azure AD aufgefüllt werden.  Die allgemeine Empfehlung von Microsoft besteht in der Synchronisierung aller Gesamtstrukturen, die Benutzeridentitäten enthalten, sowie aller Gesamtstrukturen, die Skype for Business Server enthalten.

 Wenn Identitäten von Benutzern über mehrere Gesamtstrukturen vorhanden sind, sollte Azure AD Connect die Zusammenführung ausführen. Wenn diese Anleitung befolgt wird, synchronisiert Azure AD Connect automatisch die richtigen Attribute, vorausgesetzt, Sie ändern weder die Connectors noch die Synchronisierungsregeln in Azure AD Connect. 
  
Wenn Sie nicht aus allen Gesamtstrukturen synchronisieren, die Benutzeridentitäten und die Skype for Business Server-Bereitstellung enthalten, müssen Sie dennoch sicherstellen, dass die relevanten Identitäts- und Skype for Business-Attribute für alle Benutzer, die Teams oder Skype for Business (lokal oder online) verwenden, ordnungsgemäß in Azure AD aufgefüllt werden, was wahrscheinlich eine zusätzliche lokale Verzeichnissynchronisierung erfordert. Weitere Informationen finden Sie unter [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized).

In solchen Szenarien liegt es in der Verantwortung des Kunden, eine ordnungsgemäße Konfiguration für das Auffüllen der Attribute in Azure AD sicherzustellen. Denken Sie dabei an Folgendes: 

- Die Verwendung einer nicht standardmäßigen Konfiguration für die Synchronisierung mit Azure AD ist riskant, da dies zu Fehlkonfigurationen führen könnte, was eine Beschädigung von Daten in Ihrem Onlineverzeichnis zur Folge haben könnte.

- Da sich Produkte ständig weiterentwickeln, überprüft Microsoft weiterhin standardmäßige Synchronisierungskonfigurationen, in denen alle relevanten Gesamtstrukturen synchronisiert werden. Kunden mit benutzerdefinierten Synchronisierungskonfigurationen müssen sicherstellen, dass ihre Konfigurationen die richtigen Attribute und Werte in Azure AD bereitstellen. 

## <a name="related-information"></a>Verwandte Informationen

- [Was ist Hybrididentität?](/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Azure AD Connect-Synchronisierung: Verstehen und Anpassen der Synchronisierung](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Topologien für Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD Connect-Synchronisierung: Mit Azure Active Directory synchronisierte Attribute](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)