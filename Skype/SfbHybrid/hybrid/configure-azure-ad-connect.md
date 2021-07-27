---
title: Konfigurieren von Azure AD-Verbinden
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
description: Anweisungen zum Konfigurieren von Azure AD-Verbinden in einer Hybridumgebung.
ms.openlocfilehash: 265ff29f033d6e5e1be6ee00126b4601ff3bbb64
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510626"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Konfigurieren von Azure AD Connect für Teams und Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
Organisationen, die über Skype for Business Server (oder Lync Server) lokal verfügen und entweder Teams oder Skype for Business Online verwenden möchten, müssen Azure AD Verbinden konfigurieren, um ihr lokales Verzeichnis mit Microsoft 365 oder Office 365 zu synchronisieren, wie in diesem Dokument beschrieben.  Dazu gehören Organisationen, die direkt von Skype for Business lokalen zu Teams wechseln. Insbesondere müssen Organisationen mit lokalem Skype for Business sicherstellen, dass die richtigen msRTCSIP-Attribute in Azure AD synchronisiert werden.

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Bestehende Teams Benutzer, die Skype for Business auch lokal haben, müssen ihr Konto für das lokale Skype for Business in die Cloud verschieben, um die vollständige Funktionalität zu erhalten, z. B. die Möglichkeit, mit Skype for Business-Benutzern zusammen zu arbeiten und mit Benutzer in Verbundorganisationen zu kommunizieren. Auch wenn der Benutzer nur Teams verwendet, wird dieses Skype for Business-Konto für die Infrastruktur benötigt, um die zusätzlichen Funktionen bereitzustellen.  Damit diese Migration durchgeführt werden kann, müssen Sie sicherstellen, dass Azure AD Connect ordnungsgemäß konfiguriert ist, damit Sie Hybrid aktivieren können.
 

## <a name="background-information"></a>Hintergrundinformationen

Azure Active Directory Verbinden hält Ihr lokales Active Directory kontinuierlich mit Microsoft 365 oder Office 365 synchronisiert.  Ihr lokales Verzeichnis bleibt die autorisierende Identitätsquelle, und Änderungen in Ihrer lokalen Umgebung werden in Azure AD synchronisiert. Weitere Informationen finden Sie unter [Azure AD Verbinden Sync](/azure/active-directory/hybrid/how-to-connect-sync-whatis).  Auch wenn Sie nicht alle Benutzer aus der lokalen Umgebung in die Cloud verschieben, müssen alle Benutzer, die Teams, Skype for Business lokal oder Skype for Business Online verwenden, von der lokalen Umgebung in Azure AD synchronisiert werden, um die Kommunikation zwischen lokalen und Onlinebenutzern sicherzustellen. *Benutzer in Ihrer Organisation werden sowohl in den lokalen als auch in den Onlineverzeichnissen dargestellt.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Konfigurieren von Azure AD, wenn Sie Skype for Business Server haben 

Unabhängig davon, ob Sie über eine lokale Active Directory-Gesamtstruktur oder mehrere Gesamtstrukturen verfügen, können Azure AD Verbinden in einer Vielzahl unterstützter Topologien verwendet werden, wie in [Topologien für Azure AD Verbinden](/azure/active-directory/hybrid/plan-connect-topologies)beschrieben.  Im Hinblick auf Skype for Business Server gibt es drei Hauptvarianten: 

1. Eine einzelne Gesamtstruktur, die autorisierende Benutzeridentitäten enthält und Skype for Business Server hostet. 

2. Mehrere Gesamtstrukturen, von denen jeweils nur eine Skype for Business Server hostet, sowie eine oder mehrere andere Gesamtstrukturen, die autorisierende Benutzeridentitäten (die Kontogesamtstrukturen) enthalten. 

3. Mehrere Bereitstellungen von Skype for Business Server in mehreren Gesamtstrukturen. Wenn bestimmte Anforderungen erfüllt sind, können Organisationen diese mehreren Bereitstellungen in einer einzigen Microsoft 365 oder Office 365 Organisation konsolidieren.

### <a name="single-forest"></a>Einzelne Gesamtstruktur 

Wenn Benutzerkonten und Skype for Business in einer einzigen Gesamtstruktur gehostet werden, müssen Sie sicherstellen, dass Azure AD Connect so konfiguriert ist, dass Benutzer aus dieser Gesamtstruktur mit Azure AD synchronisiert werden.  Der Installations-Assistent für Azure AD Connect bietet zwar eine Vielzahl von Optionen, die entsprechenden Attribute werden aber automatisch in Azure Active Directory synchronisiert. Kunden wird davon abgeraten, die integrierten Synchronisierungsregeln und/oder Connectors zu ändern, die die Konfiguration verwalten (was über den Installations-Assistenten nicht möglich ist).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Mehrere Gesamtstrukturen mit einer Skype for Business-Bereitstellung 

Dieses Szenario wird häufig als eine Topologie mit Ressourcengesamtstruktur bezeichnet. Die autorisierenden Identitäten der Benutzer werden in einer oder mehreren Kontengesamtstrukturen gehostet, und Skype for Business wird in einer separaten Ressourcengesamtstruktur bereitgestellt (die ihrerseits ggf. auch autorisierende Benutzeridentitäten hostet). Im Allgemeinen können sich die autorisierenden Identitäten für Skype for Business-Benutzer in der gleichen Gesamtstruktur wie Skype for Business Server und/oder in einer anderen Gesamtstruktur befinden, vorausgesetzt: 

- Benutzer, die autorisierende Identitäten aus den Kontengesamtstrukturen aufweisen, werden in der Ressourcengesamtstruktur (in der der Skype for Business-Server bereitgestellt wird) als deaktivierte Benutzerobjekte dargestellt, und das Attribut "msRTCSIP-OriginatorSID" in der Ressourcengesamtstruktur stimmt mit der SID in der Kontengesamtstruktur überein. Weitere Informationen finden Sie unter Konfigurieren einer Umgebung mit [mehreren Gesamtstrukturen für hybride Skype for Business.](configure-a-multi-forest-environment-for-hybrid.md)

- Die Ressourcengesamtstruktur, die Skype for Business Server hostet, vertraut den Kontengesamtstrukturen.  

- Alle relevanten Benutzerobjekte und Attribute für die Identität (aus der Kontengesamtstruktur) und Skype for Business (aus der Ressourcengesamtstruktur) werden mit Azure AD mit den korrekten Werten über Azure AD Connect synchronisiert.  

 Um eine ordnungsgemäße Objekt- und Attributsynchronisierung in Azure AD in einem lokalen Szenario mit [mehreren Gesamtstrukturen](configure-a-multi-forest-environment-for-hybrid.md)zu erreichen, empfiehlt Microsoft dringend die Verwendung von Azure AD-Verbinden zum Synchronisieren aus allen Gesamtstrukturen, die Benutzerkonten aktiviert haben, und der Gesamtstruktur, die Skype for Business enthält.  Wenn Sie aus allen Gesamtstrukturen synchronisieren, müssen Sie Azure AD Connect so konfigurieren, dass diese Identitäten zusammengeführt und mit Azure AD synchronisiert werden. Azure AD Connect dient zur Behandlung dieses Szenarios und bietet eine integrierte Option im Installations-Assistenten, um dies einzurichten, einschließlich Anker zum Verknüpfen von Identitäten.  Wählen Sie Folgendes aus: Benutzeridentitäten sind in mehreren Verzeichnissen vorhanden. Übereinstimmung mithilfe von --> ObjectSID- und msExchangeMasterAccountSID-Attributen.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Mehrere Bereitstellungen von Skype for Business Server in mehreren Gesamtstrukturen 

In diesem Szenario gibt es mehrere Gesamtstrukturen, die jeweils Skype for Business Server enthalten, und eine einzelne Microsoft 365 oder Office 365 Organisation.  Jede Gesamtstruktur, die Skype for Business Server enthält, kann mithilfe von AAD Verbinden in Azure AD für diese Organisation synchronisiert werden. Es kann immer nur höchstens eine Gesamtstruktur für die Skype for Business-Hybridbereitstellung konfiguriert werden. Vor dem Aktivieren der Hybridbereitstellung in einer Gesamtstruktur müssen alle SIP-Domänen aus allen anderen Gesamtstrukturen mithilfe von [disable-csonlineSipDomain](/powershell/module/skype/disable-csonlinesipdomain)deaktiviert werden. Weitere Informationen zum Konsolidieren einer solchen Umgebung in Microsoft 365 oder Office 365 finden Sie unter [Cloudkonsolidierung für Teams und Skype for Business.](cloud-consolidation.md)

## <a name="general-requirements"></a>Allgemeine Anforderungen 

Sowohl die Teams als auch Skype for Business Onlinedienste erfordern, dass die richtigen Active Directory-Attribute vorhanden sind und in Azure AD aufgefüllt werden.  Microsoft empfiehlt generell, alle Gesamtstrukturen zu synchronisieren, die Benutzeridentitäten sowie alle Gesamtstrukturen enthalten, die Skype for Business Server enthalten.

 Wenn Identitäten von Benutzern über mehrere Gesamtstrukturen vorhanden sind, sollte Azure AD Connect die Zusammenführung ausführen. Wenn diese Anleitung befolgt wird, synchronisiert Azure AD Verbinden automatisch die richtigen Attribute, vorausgesetzt, Sie ändern weder die Connectors noch die Synchronisierungsregeln in Azure AD Verbinden. 
  
Wenn Sie nicht aus allen Gesamtstrukturen synchronisieren, die Benutzeridentitäten und die Skype for Business Server Bereitstellung enthalten, müssen Sie dennoch sicherstellen, dass die relevanten Identitäten und Skype for Business Attribute für alle Benutzer, die Teams oder Skype for Business (lokal oder online) verwenden, korrekt in Azure AD aufgefüllt werden – was wahrscheinlich eine zusätzliche lokale Verzeichnissynchronisierung erfordert. Weitere Informationen finden Sie unter [Azure AD Verbinden Synchronisierung: Mit Azure Active Directory synchronisierte Attribute.](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

In solchen Szenarien liegt es in der Verantwortung des Kunden, eine ordnungsgemäße Konfiguration für das Auffüllen der Attribute in Azure AD sicherzustellen. Denken Sie dabei an Folgendes: 

- Die Verwendung einer nicht standardmäßigen Konfiguration für die Synchronisierung mit Azure AD ist riskant, da dies zu Fehlkonfigurationen führen könnte, was eine Beschädigung von Daten in Ihrem Onlineverzeichnis zur Folge haben könnte.

- Da sich Produkte ständig weiterentwickeln, überprüft Microsoft weiterhin standardmäßige Synchronisierungskonfigurationen, in denen alle relevanten Gesamtstrukturen synchronisiert werden. Kunden mit benutzerdefinierten Synchronisierungskonfigurationen müssen sicherstellen, dass ihre Konfigurationen die richtigen Attribute und Werte in Azure AD bereitstellen. 

## <a name="related-information"></a>Verwandte Informationen

- [Was ist hybride Identität?](/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Azure AD Verbinden-Synchronisierung: Verstehen und Anpassen der Synchronisierung](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Topologien für Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD Verbinden-Synchronisierung: Mit Azure Active Directory synchronisierte Attribute](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)