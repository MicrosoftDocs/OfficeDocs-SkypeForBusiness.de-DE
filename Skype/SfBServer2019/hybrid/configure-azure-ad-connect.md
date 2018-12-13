---
title: Konfigurieren von Azure Active Directory verbinden
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Anleitung für die Konfiguration von Azure Active Directory verbinden in einer hybridumgebung.
ms.openlocfilehash: 5d27de4786c588d5d2f2a276dc20c25436bada98
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/13/2018
ms.locfileid: "27244116"
---
# <a name="configure-azure-ad-connect-for-skype-for-business-and-teams"></a>Konfigurieren von Azure AD Connect für Skype für Unternehmen und Teams 
 
Organisationen, deren lokalen Skype für Business Server (oder Lync Server) und planen, die für Business Online Teams oder Skype verwenden, müssen wie in diesem beschrieben Azure AD-verbinden, um ihre lokalen Verzeichnis mit Office 365, synchronisieren konfigurieren Dokument.  Dazu gehören Organisationen, die direkt von Skype für Business lokale Teams verschieben. Insbesondere müssen Organisationen mit Skype für Business lokal sicherstellen, dass die richtigen MsRTCSIP-Attribute in Azure Active Directory synchronisiert werden. 

> [!NOTE]
> Vorhandene Teams Benutzer auch Skype für Business lokal benötigen ihre Skype für Business lokale Konto in die Cloud, um die erste vollständige Funktionalität – wie etwa die Möglichkeit für Unternehmensbenutzer und Zusammenarbeit mit Skype verschoben kommunizieren Sie mit Benutzern in Partnerorganisationen. Auch wenn der Benutzer nur Teams verwenden, ist dieser online Skype für Business-Konto von der Infrastruktur erforderlich, um zusätzliche Funktionen bereitzustellen.  Bei dieser Migration stattfinden müssen Sie sicherstellen, dass Azure AD-Connect ordnungsgemäß konfiguriert ist, damit Sie Hybrid aktivieren können.
 

## <a name="background-information"></a>Hintergrundinformationen

Azure Active Directory verbinden, behält die lokale Active Directory ständig mit Office 365 synchronisiert.  Ihr lokales Verzeichnis bleibt die autoritative Quelle der Identität und Änderungen aus Ihrer lokalen Umgebung in Azure AD synchronisiert werden. Weitere Informationen finden Sie unter [Azure AD-Synchronisierung zum Verbinden](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis).  Auch wenn Sie nicht alle Benutzer aus der lokalen in die Cloud verschieben, müssen alle Benutzer, mit denen Teams, Skype für Business lokal oder Skype für Business Online lokal in Azure AD, um sicherzustellen, dass die Kommunikation zwischen lokalen und online-Benutzer synchronisiert werden . *Benutzer in Ihrer Organisation werden in Ihrer lokalen und online Verzeichnisse dargestellt.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Konfigurieren von Azure AD, wenn Sie Skype für Business Server haben 

Ob Sie eine lokale Active Directory-Gesamtstruktur oder mehrere Gesamtstrukturen haben, kann in einer Vielzahl von unterstützten Topologien, gemäß der Beschreibung in [Topologien für Azure Active Directory verbinden](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)Azure AD-Verbindung verwendet werden.  Aus der Sicht von Skype für Business Server gibt es drei wichtigste Varianten: 

1. Eine einzelne Gesamtstruktur, die enthält autorisierende Benutzeridentitäten und Skype für Business Server hostet. 

2. Mehrere Gesamtstrukturen, von denen nur eine Skype für Business Server gehostet wird, sowie mindestens einen anderen Gesamtstrukturen, die autorisierende Benutzeridentitäten (das Konto Gesamtstrukturen) enthalten. 

3. Mehrere Bereitstellungen von Skype für Business Server in mehreren Gesamtstrukturen. Sofern bestimmte Anforderungen erfüllt sind, können Organisationen diese Bereitstellungen mit mehreren in einer einzelnen Office 365-Mandanten konsolidieren.

### <a name="single-forest"></a>Einzelne Gesamtstruktur 

Wenn Benutzerkonten und Skype für Unternehmen alle in einer einzelnen Gesamtstruktur gehostet werden, müssen Sie sicherstellen, dass Azure AD-Connect konfiguriert ist, um Benutzer aus der Gesamtstruktur in Azure AD zu synchronisieren.  Obwohl der Installations-Assistent für Azure Active Directory verbinden eine Vielzahl von Optionen verfügt, werden automatisch die entsprechenden Attribute in Azure Active Directory synchronisiert werden. Kunden sollten vor der integrierten Synchronisierungsregeln und/oder Stecker die Verwaltung der Konfiguration (Dies ist nicht möglich, von der Installations-Assistent) ändern.  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Mehrere Gesamtstrukturen mit einer Skype für die Business-Bereitstellung 

In diesem Szenario wird häufig als einer Topologie mit Ressourcengesamtstruktur bezeichnet. Autorisierende Benutzeridentität in einer oder mehreren Konto Gesamtstrukturen gehostet werden, und Skype für Unternehmen in einer separaten Ressourcengesamtstruktur bereitgestellt wird (die selbst hosten möglicherweise auch autorisierende Benutzeridentitäten). Im Allgemeinen kann Skype für Geschäftsbenutzer autorisierende Identitäten in derselben Gesamtstruktur wie Skype für Business Server und/oder in einer anderen Gesamtstruktur bereitgestellt: 

- Benutzer mit autorisierende Identitäten aus der Konto-Gesamtstrukturen aufgelistet werden als deaktivierte Benutzerobjekte in der Ressourcengesamtstruktur (wobei Skype für Business Server bereitgestellt wird) und das Attribut MsRTCSIP-OriginatorSID in der Ressourcengesamtstruktur entspricht der SID in der Kontostruktur. Weitere Informationen finden Sie unter [Konfigurieren einer Umgebung mit mehreren Gesamtstrukturen für hybride Skype für Unternehmen](configure-a-multi-forest-environment-for-hybrid.md).

- Die Ressourcengesamtstruktur hostet Skype für Business Server vertraut der Konto-Gesamtstrukturen aufgelistet.  

- Alle relevanten User-Objekte und Attribute für sowohl Identität (aus Konto Gesamtstrukturen) und Skype für Unternehmen (von der Ressourcengesamtstruktur) werden in Azure Active Directory mit den richtigen Werten über Azure AD-Connect synchronisiert.  

 Um die richtige Objekt und Attribut Synchronisierung in Azure AD in einer [Gesamtstruktur mit mehreren lokalen Szenario](configure-a-multi-forest-environment-for-hybrid.md)zu erzielen, Microsoft empfiehlt mit Azure AD-verbinden für die Synchronisierung von allen Gesamtstrukturen, die Benutzerkonten aktiviert haben und der Gesamtstruktur, Skype für Business enthält.  Vorausgesetzt, dass Sie über alle Gesamtstrukturen synchronisieren, müssen Sie dann konfigurieren Azure AD-verbinden, um diese Identitäten zusammenführen und Azure AD synchronisieren. Azure Active Directory verbinden ist darauf ausgelegt, dieses Szenario zu behandeln und bietet eine integrierte Option in der Installations-Assistent dies einrichten einschließlich der Einrichtung von Anker um Identitäten teilzunehmen.  Wählen Sie die folgenden: Benutzeridentitäten über mehrere Verzeichnisse vorhanden sind. Übereinstimmung mit--> Objekt-SID und MsExchangeMasterAccountSID Attribute.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Mehrere Skype für Business Server-Bereitstellungen in mehreren Gesamtstrukturen 

In diesem Szenario sind mehrere Gesamtstrukturen, jede enthaltenden Skype für Business Server und einer einzelnen Office 365-Mandanten.  Jede Gesamtstruktur mit Skype für Business Server für diese AAD Verbinden mit Mandanten in Azure Active Directory synchronisiert werden können. Höchstens kann nur einer Gesamtstruktur für Skype für hybride Business zu einem bestimmten Zeitpunkt konfiguriert werden. Bevor Sie Hybrid in einer Gesamtstruktur aktivieren, müssen alle SIP-Domänen aus allen anderen Gesamtstrukturen mit [Disable-CsonlineSipDomain](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain)deaktiviert werden. Weitere Einzelheiten zur Anzeige einer solchen Umgebung in Office 365 konsolidieren finden Sie unter [Cloud Konsolidierung für Teams und Skype für Unternehmen](cloud-consolidation.md).

## <a name="general-requirements"></a>Allgemeine Anforderungen 

Sowohl der Teams und Skype für Business Online-Dienste erfordern, dass die richtigen Active Directory-Attribute vorhanden sind und in Azure AD aufgefüllt werden.  Allgemeine Empfehlung von Microsoft ist zu synchronisierenden alle Gesamtstrukturen, die Benutzeridentitäten enthalten sowie alle Gesamtstrukturen, die Skype für Business Server enthalten.

 Benutzeridentität in mehreren Gesamtstrukturen vorhanden, tun Azure Active Directory verbinden den Seriendruck, wenn. Wenn dieser Anleitung des Telefonfestnetzes verwendet wird, werden Azure Active Directory verbinden die richtigen Attribute aufgeführt, sofern Sie nicht die Connectors oder Sync Regeln in Azure AD-Connect ändern automatisch synchronisiert. 
  
Wenn Sie nicht über alle Gesamtstrukturen, die Benutzeridentitäten und die Skype für Business Server-Bereitstellung enthalten synchronisiert werden, müssen Sie dennoch die relevante Identität sicherstellen und Skype für Business Attribute sind ordnungsgemäß in Azure Active Directory für jeden Benutzer von Teams oder Skype gefüllt für Unternehmen (, ob der lokale oder online) – die wird wahrscheinlich zusätzliche erfordern lokale-Directory-Synchronisierung. Weitere Informationen finden Sie unter [Verbinden von Azure AD-Synchronisierung: Attribute mit Azure Active Directory synchronisiert](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized).

In diesen Fällen ist es der Verantwortung des Kunden um sicherzustellen, dass der korrekten Konfiguration für die Attribute in Azure AD auffüllen. Berücksichtigen Sie dabei Folgendes: 

- Verwenden eine nicht standardmäßige Konfiguration für das Synchronisieren von Azure AD ist riskant, da es zu einer fehlerhaften Konfiguration, wodurch Beschädigung der Daten in Ihrem Verzeichnis online könnte führen kann.

- Weiterentwicklung von Produkten wird weiterhin Microsoft standard Synchronisierung Konfigurationen Vergewissern Sie sich in denen alle relevante Gesamtstrukturen synchronisiert werden. Kunden mit benutzerdefinierten Synchronisierung Konfigurationen sind dafür verantwortlich, sicherzustellen, dass ihre Konfigurationen in Azure AD die richtigen Attribute und Werte liefern. 

## <a name="related-information"></a>Verwandte Informationen

- [Was ist Hybrid Identity](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/whatis-hybrid-identity?toc=%2Fen-us%2Fazure%2Factive-directory%2Fhybrid%2FTOC.json&bc=%2Fen-us%2Fazure%2Fbread%2Ftoc.json)

- [Azure Active Directory verbinden Sync: Verständnis und die Synchronisierung anpassen](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Verbinden von Topologien für Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure Active Directory verbinden Sync: Attribute mit Azure Active Directory synchronisiert.](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
