---
title: Konfigurieren Azure AD Connect
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Anweisungen zum Konfigurieren Azure AD Connect in einer Hybridumgebung.
ms.openlocfilehash: 9df0e42224d3186c3d7b5b1748412e9ec9121897
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160579"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Konfigurieren Azure AD Connect für Teams und Skype for Business
 
Organisationen, die lokal Skype for Business Server (oder lync Server) haben und die Teams oder Skype for Business Online verwenden möchten, müssen Azure AD Connect so konfigurieren, dass Ihr lokales Verzeichnis mit Office 365 synchronisiert wird, wie in diesem Abschnitt beschrieben. Dokument.  Dies umfasst Organisationen, die direkt von Skype for Business lokal zu Microsoft Teams migrieren. Insbesondere müssen Organisationen mit Skype for Business lokal sicherstellen, dass die richtigen msRTCSIP-Attribute in Azure AD synchronisiert werden. 

> [!NOTE]
> Vorhandene Microsoft Teams-Benutzer, die auch lokal Skype for Business haben, müssen Ihr Skype for Business lokales Konto in die Cloud verschieben, um vollständige Funktionalität zu erhalten, beispielsweise die Möglichkeit zur Zusammenarbeit mit Skype for Business-Benutzern und Kommunikation mit Benutzern in Verbundorganisationen. Selbst wenn der Benutzer nur Teams verwendet, wird dieses Online Skype for Business Konto von der Infrastruktur benötigt, um die zusätzliche Funktionalität zu liefern.  Damit diese Migration stattfinden kann, müssen Sie sicherstellen, dass Azure AD Connect ordnungsgemäß konfiguriert ist, damit Sie Hybrid aktivieren können.
 

## <a name="background-information"></a>Hintergrundinformationen

Azure Active Directory Connect hält Ihre lokalen Active Directory kontinuierlich mit Office 365 synchronisiert.  Ihr lokales Verzeichnis bleibt die autorisierende Identitäts Quelle, und Änderungen aus der lokalen Umgebung werden in Azure AD synchronisiert. Weitere Informationen finden Sie unter [Azure AD Connect Sync](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis).  Selbst wenn Sie nicht alle Benutzer aus der lokalen Umgebung in die Cloud verschieben, müssen alle Benutzer, die Teams verwenden, Skype for Business lokal oder Skype for Business Online von lokal in Azure AD synchronisiert werden, um die Kommunikation zwischen lokalen und Online Benutzern sicherzustellen. . *Benutzer in Ihrer Organisation werden sowohl in Ihren lokalen als auch in Online-Verzeichnissen dargestellt.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Konfigurieren von Azure AD, wenn Sie Skype for Business Server haben 

Unabhängig davon, ob Sie über eine lokale Active Directory Gesamtstruktur oder mehrere Gesamtstrukturen verfügen, kann Azure AD Connect in einer Vielzahl unterstützter Topologien verwendet werden, wie in [Topologien für Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)beschrieben.  Aus der Perspektive von Skype for Business Server gibt es drei Hauptvariationen: 

1. Eine einzelne Gesamtstruktur, die autorisierende Benutzeridentitäten und Hosts Skype for Business Server enthält. 

2. Mehrere Gesamtstrukturen, von denen nur einer hostet Skype for Business Server, sowie eine oder mehrere andere Gesamtstrukturen, die autorisierende Benutzeridentitäten (die Konto Gesamtstrukturen) enthalten. 

3. Mehrere Bereitstellungen von Skype for Business Server in mehreren Gesamtstrukturen. Wenn bestimmte Anforderungen erfüllt sind, können Organisationen diese mehrere Bereitstellungen in einem einzigen Office 365 Mandanten konsolidieren.

### <a name="single-forest"></a>Einzelne Gesamtstruktur 

Wenn Benutzerkonten und Skype for Business alle in einer einzelnen Gesamtstruktur gehostet werden, müssen Sie sicherstellen, dass Azure AD Connect so konfiguriert ist, dass Benutzer aus dieser Gesamtstruktur in Azure AD synchronisiert werden.  Obwohl der Installations-Assistent für Azure AD Connect eine Vielzahl von Optionen enthält, werden die entsprechenden Attribute automatisch in Azure Active Directory synchronisiert. Kunden wird empfohlen, die integrierten Synchronisierungsregeln und/oder Connectors zu ändern, die die Konfiguration verwalten (was im Installations-Assistenten nicht möglich ist).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Mehrere Gesamtstrukturen mit einer Skype for Business-Bereitstellung 

Dieses Szenario wird häufig als Topologie einer Ressourcengesamtstruktur bezeichnet. Die autorisierenden Identitäten der Benutzer werden in einer oder mehreren Konto Gesamtstrukturen gehostet, und Skype for Business wird in einer separaten Ressourcengesamtstruktur bereitgestellt (die selbst möglicherweise auch autorisierende Benutzeridentitäten hostet). Im Allgemeinen können sich Skype for Business autorisierenden Identitäten der Benutzer in der gleichen Gesamtstruktur wie Skype for Business Server und/oder in einer anderen Gesamtstruktur befinden, vorausgesetzt: 

- Benutzer mit autorisierenden Identitäten aus den Konto Gesamtstrukturen werden in der Ressourcengesamtstruktur (wobei Skype for Business Server bereitgestellt wird) als deaktivierte Benutzerobjekte dargestellt, und das msRTCSIP-OriginatorSID-Attribut in der Ressourcengesamtstruktur entspricht der SID im Kontogesamtstruktur. Weitere Informationen finden Sie unter [Konfigurieren einer Umgebung mit mehreren Gesamtstrukturen für Hybrid Skype for Business](configure-a-multi-forest-environment-for-hybrid.md).

- Die Ressourcengesamtstruktur, die Skype for Business Server hostet, vertraut den Konto Gesamtstrukturen.  

- Alle relevanten Benutzerobjekte und Attribute für die Identität (aus Konto Gesamtstrukturen) und Skype for Business (aus der Ressourcengesamtstruktur) werden mit den korrekten Werten über Azure AD Connect in Azure AD synchronisiert.  

 Um eine ordnungsgemäße Objekt-und Attribut Synchronisierung in Azure AD in einem [lokalen Szenario mit mehreren Gesamtstrukturen](configure-a-multi-forest-environment-for-hybrid.md)zu erreichen, empfiehlt Microsoft dringend die Verwendung von Azure AD Connect zur Synchronisierung von allen Gesamtstrukturen mit aktivierten Benutzerkonten und der Gesamtstruktur, die enthält Skype for Business.  Wenn Sie von allen Gesamtstrukturen aus synchronisieren, müssen Sie Azure AD Connect konfigurieren, um diese Identitäten zusammenzuführen und mit Azure AD zu synchronisieren. Azure AD Connect wurde entwickelt, um dieses Szenario zu verarbeiten, und stellt eine integrierte Option im Installations-Assistenten bereit, um diese einzurichten, einschließlich der Einrichtung von Anker für die Teilnahme an Identitäten.  Wählen Sie Folgendes aus: Benutzeridentitäten sind in mehreren Verzeichnissen vorhanden. Übereinstimmung mit--#a0-Objekten und msexchangemasteraccount sid aus-Attributen.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Mehrere Skype for Business Server-Bereitstellungen in mehreren Gesamtstrukturen 

In diesem Szenario gibt es mehrere Gesamtstrukturen, die jeweils Skype for Business Server und einen einzelnen Office 365 Mandanten enthalten.  Jede Gesamtstruktur, die Skype for Business Server enthält, kann mit Aad Connect in Azure AD für diesen Mandanten synchronisiert werden. Höchstens kann nur eine Gesamtstruktur für Skype for Business Hybrid zu einem bestimmten Zeitpunkt konfiguriert werden. Vor dem Aktivieren von Hybrid in einer Gesamtstruktur müssen alle SIP-Domänen aus allen anderen Gesamtstrukturen mithilfe von [Disable-csonlineSipDomain](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain)deaktiviert werden. Weitere Informationen zum Konsolidieren einer solchen Umgebung in Office 365 finden Sie unter [Cloud Consolidation for Teams and Skype for Business](cloud-consolidation.md).

## <a name="general-requirements"></a>Allgemeine Anforderungen 

Sowohl für die Teams-als auch für den Skype for Business Online-Dienste ist es erforderlich, dass die richtigen Active Directory Attribute vorhanden sind und in Azure AD aufgefüllt werden.  Die allgemeine Empfehlung von Microsoft besteht darin, alle Gesamtstrukturen mit Benutzeridentitäten sowie alle Gesamtstrukturen zu synchronisieren, die Skype for Business Server enthalten.

 Wenn die Identität von Benutzern in mehreren Gesamtstrukturen vorhanden ist, sollte Azure AD Connect die Zusammenführung durchführen. Wenn dieser Leitfaden befolgt wird, synchronisiert Azure AD Connect automatisch die richtigen Attribute, vorausgesetzt, Sie ändern weder die Connectors-noch die Synchronisierungsregeln in Azure AD Connect. 
  
Wenn Sie nicht von allen Gesamtstrukturen mit Benutzeridentitäten und der Skype for Business Server-Bereitstellung synchronisieren, müssen Sie dennoch sicherstellen, dass die relevanten Identitäts-und Skype for Business Attribute ordnungsgemäß in Azure AD für einen beliebigen Benutzer mit Microsoft Teams oder Skype aufgefüllt werden. für Unternehmen (lokal oder Online)--was voraussichtlich eine zusätzliche lokale Verzeichnissynchronisierung erforderlich ist. Weitere Informationen finden Sie unter [Azure AD Connect Sync: Attribute Synchronized to Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized).

In solchen Szenarien ist es Aufgabe des Kunden, eine ordnungsgemäße Konfiguration zum Auffüllen der Attribute in Azure AD sicherzustellen. Denken Sie dabei an Folgendes: 

- Die Verwendung einer nicht standardmäßigen Konfiguration für die Synchronisierung mit Azure AD ist riskant, da dies zu Fehlkonfigurationen führen könnte, was zu Datenbeschädigungen in Ihrem Online Verzeichnis führen könnte.

- Wenn sich Produkte entwickeln, überprüft Microsoft weiterhin Standard Synchronisierungs Konfigurationen, in denen alle relevanten Gesamtstrukturen synchronisiert sind. Kunden mit benutzerdefinierten Synchronisierungs Konfigurationen sind dafür verantwortlich, sicherzustellen, dass Ihre Konfigurationen die richtigen Attribute und Werte in Azure AD liefern. 

## <a name="related-information"></a>Weitere Informationen

- [Was ist eine hybride Identität?](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/whatis-hybrid-identity?toc=%2Fen-us%2Fazure%2Factive-directory%2Fhybrid%2FTOC.json&bc=%2Fen-us%2Fazure%2Fbread%2Ftoc.json)

- [Azure AD Connect Sync: verstehen und Anpassen der Synchronisierung](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Topologien für Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD Connect Sync: Attribute, die mit Azure synchronisiert werden Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
