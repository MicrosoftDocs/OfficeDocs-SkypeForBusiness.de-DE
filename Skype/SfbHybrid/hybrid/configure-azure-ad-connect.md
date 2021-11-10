---
title: Konfigurieren Azure AD Verbinden
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
description: Anweisungen zum Konfigurieren von Azure AD Verbinden in einer Hybridumgebung.
ms.openlocfilehash: cfb290ecc6892001a9e20d9260c54c076a51dfe3
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2021
ms.locfileid: "60887213"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Konfigurieren von Azure AD Connect für Teams und Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
Um Teams zu verwenden, müssen Organisationen mit einer lokalen Bereitstellung von Skype for Business Server oder Lync Server 2013 Azure AD Verbinden konfigurieren, um ihr lokales Verzeichnis mit Microsoft 365 zu synchronisieren. Organisationen mit Skype for Business Server lokalen Bereitstellung müssen sicherstellen, dass die richtigen msRTCSIP-Attribute in Azure AD synchronisiert werden. In diesem Artikel gilt jeder Verweis auf "Skype for Business Server" auch für Lync Server 2013.

> [!NOTE]
> - Um die volle Funktionalität zu erhalten, müssen vorhandene Teams Benutzer, die auch Skype for Business lokal haben, ihr Skype for Business lokalen Konto in die Cloud verschieben lassen. Um beispielsweise Funktionen wie die Möglichkeit zur Zusammenarbeit mit Skype for Business Benutzern und zur Kommunikation mit Benutzern in Verbundorganisationen zu erhalten. Wenn der lokale Benutzer nur Teams verwendet, müssen Sie den Benutzer trotzdem in die Cloud verschieben, um vollständige Teams Funktionen als TeamsOnly-Benutzer bereitzustellen. Damit diese Migration stattfindet, müssen Sie Azure AD Verbinden konfigurieren, damit Sie hybrid aktivieren können.
> - Wenn Sie nicht planen, Benutzer in Kürze von der lokalen Bereitstellung in die Cloud zu verschieben, müssen Sie Azure AD Verbinden dennoch so konfigurieren, dass die Teams und die Skype for Business Server Konten gleichzeitig vorhanden sind.
 

## <a name="background-information"></a>Hintergrundinformationen

Azure Active Directory Verbinden hält Ihr lokales Active Directory kontinuierlich mit Microsoft 365 synchronisiert. Ihr lokales Verzeichnis bleibt die autorisierende Identitätsquelle, während Änderungen aus Ihrer lokalen Umgebung in Azure AD synchronisiert werden. Weitere Informationen finden Sie unter [Azure AD Verbinden Sync](/azure/active-directory/hybrid/how-to-connect-sync-whatis).  *Benutzer in Ihrer Organisation werden sowohl in Ihren lokalen als auch in Onlineverzeichnissen repräsentiert.*  Alle Benutzer, die Teams oder Skype for Business lokal verwenden, müssen lokal in Azure AD synchronisiert werden, um die Koexistenz dieser Konten sicherzustellen. Darüber hinaus können Sie die Kommunikation zwischen lokalen und Onlinebenutzern über Skype for Business Hybridkonnektivität vereinfachen, was auch die Konfiguration von Azure AD Verbinden erfordert.


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Konfigurieren von Azure AD, wenn Sie Skype for Business Server haben 

### <a name="general-requirements"></a>Allgemeine Anforderungen 

Damit eine lokale Bereitstellung von Skype for Business Server mit Teams zusammenarbeiten kann, müssen bestimmte Active Directory-Attribute aus der lokalen Bereitstellung mithilfe von Azure AD Verbinden in Azure AD synchronisiert werden. Setup für Azure AD Verbinden konfiguriert automatisch die erforderlichen Attribute, die standardmäßig synchronisiert werden, wenn das Vorhandensein von Skype for Business Server in Ihrer lokalen Umgebung erkannt wird. Diese Attribute umfassen allgemeine Identitätsattribute, z. B. den Benutzerprinzipalnamen, sowie Attribute, die "msRTCSIP" vorangestellt sind, die für Skype For Business Server spezifisch sind. Der vollständige Satz von Attributen wird bei [Azure AD Verbinden Synchronisierung aufgelistet: Attribute, die mit Azure Active Directory synchronisiert werden.](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized#teams-and-skype-for-business-online)

Wenn Sie die Synchronisierungseinstellungen in Azure AD Verbinden anpassen möchten, müssen Sie sicherstellen, dass die folgenden Attribute für Benutzerobjekte synchronisiert werden:
</br>

|Attribut|Beschreibung|
|---|---|
|msRTCSIP-PrimaryUserAddress| Die SIP-Adresse des Benutzers in der lokalen Umgebung|
|msRTCSIP-DeploymentLocator| Gibt an, ob der Benutzer lokal oder in der Cloud verwaltet wird.|
|msRTCSIP-UserEnabled| Gibt an, ob der Benutzer für SIP-Funktionen aktiviert ist.|
|||

</br>
</br>
Darüber hinaus müssen Sie beim Verwalten von Telefonsystemattributen über Ihre lokale Bereitstellung auch die folgenden Attribute synchronisieren:

|Attribut|Beschreibung|
|:---|:---|
|msRTCSIP-Line| Die Telefonnummer des Benutzers|
|msRTCSIP-OptionFlags| Gibt an, ob der Benutzer für die Sprachfunktion aktiviert ist.|
|msRTCSIP-OwnerUrn| Wird verwendet, um Hybridanwendungsendpunkte zu identifizieren|
|||

</br>
Microsoft empfiehlt, alle Gesamtstrukturen zu synchronisieren, die Benutzeridentitäten sowie alle Gesamtstrukturen enthalten, die Skype for Business Server enthalten. Wenn Identitäten von Benutzern über mehrere Gesamtstrukturen vorhanden sind, sollte Azure AD Connect die Zusammenführung ausführen. Wenn Sie diesen Leitfaden befolgen, synchronisiert Azure AD Connect automatisch die richtigen Attribute, vorausgesetzt, dass Sie die Connectors oder Synchronisierungsregeln in Azure AD Connect nicht ändern. 
  
Wenn Sie nicht aus allen Gesamtstrukturen synchronisieren, die Benutzeridentitäten und die Skype for Business Server Bereitstellung enthalten, müssen Sie sicherstellen, dass die relevanten Identitäten und Skype for Business Attribute für alle Benutzer, die Teams oder Skype for Business (lokal oder online) verwenden, ordnungsgemäß in Azure AD aufgefüllt werden. Dies erfordert wahrscheinlich eine zusätzliche lokale Verzeichnissynchronisierung. Weitere Informationen finden Sie unter [Azure AD Verbinden Synchronisierung: Mit Azure Active Directory synchronisierte Attribute.](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

Es liegt in der Verantwortung des Kunden, eine ordnungsgemäße Konfiguration für das Auffüllen der Attribute in Azure AD sicherzustellen. Denken Sie dabei an Folgendes: 

- Die Verwendung einer nicht standardmäßigen Konfiguration für die Synchronisierung mit Azure AD ist riskant. Nicht standardmäßige Konfigurationen können zu Datenbeschädigungen in Ihrem Onlineverzeichnis führen.

- Da sich Produkte ständig weiterentwickeln, überprüft Microsoft weiterhin standardmäßige Synchronisierungskonfigurationen, in denen alle relevanten Gesamtstrukturen synchronisiert werden. Kunden mit benutzerdefinierten Synchronisierungskonfigurationen müssen sicherstellen, dass ihre Konfigurationen die richtigen Attribute und Werte in Azure AD bereitstellen. 

Unabhängig davon, ob Sie über eine lokale Active Directory-Gesamtstruktur oder mehrere Gesamtstrukturen verfügen, können Azure AD Verbinden in einer Vielzahl unterstützter Topologien verwendet werden, wie in [Topologien für Azure AD Verbinden](/azure/active-directory/hybrid/plan-connect-topologies)beschrieben. Im Hinblick auf Skype for Business Server gibt es drei Varianten: 

1. Eine einzelne Gesamtstruktur, die autorisierende Benutzeridentitäten enthält und Skype for Business Server hostet. 

2. Mehrere Gesamtstrukturen, von denen jeweils nur eine Skype for Business Server hostet, sowie eine oder mehrere andere Gesamtstrukturen, die autorisierende Benutzeridentitäten (die Kontogesamtstrukturen) enthalten. 

3. Mehrere Bereitstellungen von Skype for Business Server in mehreren Gesamtstrukturen. Wenn bestimmte Anforderungen erfüllt sind, können Organisationen diese mehreren Bereitstellungen in einer einzigen Microsoft 365 Organisation konsolidieren.

### <a name="single-forest"></a>Einzelne Gesamtstruktur 

Wenn Benutzerkonten und Skype for Business in einer einzigen Gesamtstruktur gehostet werden, müssen Sie sicherstellen, dass Azure AD Connect so konfiguriert ist, dass Benutzer aus dieser Gesamtstruktur mit Azure AD synchronisiert werden.  Standardmäßig werden die entsprechenden Attribute automatisch in Azure Active Directory synchronisiert. Kunden wird davon abgeraten, die integrierten Synchronisierungsregeln und/oder Connectors zu ändern, die die Konfiguration verwalten (was über den Installations-Assistenten nicht möglich ist).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Mehrere Gesamtstrukturen mit einer Skype for Business-Bereitstellung 

Dieses Szenario wird häufig als eine Topologie mit Ressourcengesamtstruktur bezeichnet. Die autorisierenden Identitäten der Benutzer werden in einer oder mehreren Kontengesamtstrukturen gehostet, und Skype for Business wird in einer separaten Ressourcengesamtstruktur bereitgestellt (die ihrerseits ggf. auch autorisierende Benutzeridentitäten hostet). Im Allgemeinen können sich die autorisierenden Identitäten für Skype for Business-Benutzer in der gleichen Gesamtstruktur wie Skype for Business Server und/oder in einer anderen Gesamtstruktur befinden, vorausgesetzt: 

- Benutzer mit autorisierenden Identitäten aus der/den Kontogesamtstruktur(n) werden in der Ressourcengesamtstruktur (in der Skype for Business Server bereitgestellt wird) als deaktivierte Benutzerobjekte dargestellt. Das Attribut "msRTCSIP-OriginatorSID" in der Ressourcengesamtstruktur muss mit der SID in der Kontogesamtstruktur übereinstimmen. Weitere Informationen finden Sie unter Konfigurieren einer Umgebung mit [mehreren Gesamtstrukturen für hybride Skype for Business.](configure-a-multi-forest-environment-for-hybrid.md)

- Die Ressourcengesamtstruktur, die Skype for Business Server hostet, vertraut den Kontengesamtstrukturen.  

- Alle relevanten Benutzerobjekte und Attribute für Identitäten (aus Kontogesamtstrukturen) und Skype for Business (aus der Ressourcengesamtstruktur) werden über Azure AD Verbinden in Azure AD mit den richtigen Werten synchronisiert.  

  Um eine ordnungsgemäße Objekt- und Attributsynchronisierung in Azure AD in einem lokalen Szenario mit [mehreren Gesamtstrukturen](configure-a-multi-forest-environment-for-hybrid.md)zu erreichen, empfiehlt Microsoft dringend, Azure AD Verbinden zum Synchronisieren aller Gesamtstrukturen zu verwenden, die Benutzerkonten und die Gesamtstruktur aktiviert haben, die Skype for Business enthält. Wenn Sie aus allen Gesamtstrukturen synchronisieren, müssen Sie Azure AD Connect so konfigurieren, dass diese Identitäten zusammengeführt und mit Azure AD synchronisiert werden. Azure AD Connect dient zur Behandlung dieses Szenarios und bietet eine integrierte Option im Installations-Assistenten, um dies einzurichten, einschließlich Anker zum Verknüpfen von Identitäten. Wählen Sie Folgendes aus: **Benutzeridentitäten sind in mehreren Verzeichnissen vorhanden,** und **"Match" mithilfe von --> ObjectSID- und msExchangeMasterAccountSID-Attributen.**


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Mehrere Bereitstellungen von Skype for Business Server in mehreren Gesamtstrukturen 

In diesem Szenario gibt es mehrere Gesamtstrukturen, die jeweils Skype for Business Server und eine einzelne Microsoft 365 Organisation enthalten. Jede Gesamtstruktur mit Skype for Business Server kann mit Azure AD Verbinden in Azure AD für diese Organisation synchronisiert werden. Es kann immer nur höchstens eine Gesamtstruktur für die Skype for Business-Hybridbereitstellung konfiguriert werden. Vor dem Aktivieren der Hybridbereitstellung in einer Gesamtstruktur müssen alle SIP-Domänen aus allen anderen Gesamtstrukturen mithilfe von [disable-csonlineSipDomain](/powershell/module/skype/disable-csonlinesipdomain)deaktiviert werden. Weitere Informationen finden Sie unter [Cloudkonsolidierung für Teams und Skype for Business.](cloud-consolidation.md)


## <a name="related-information"></a>Verwandte Informationen

- [Was ist hybride Identität?](/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Azure AD Connect-Synchronisierung: Verstehen und Anpassen der Synchronisierung](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Topologien für Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD Verbinden Synchronisierung: Mit Azure Active Directory synchronisierte Attribute](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
