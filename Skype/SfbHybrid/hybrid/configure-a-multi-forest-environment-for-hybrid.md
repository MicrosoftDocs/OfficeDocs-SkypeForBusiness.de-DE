---
title: Bereitstellen einer Topologie mit Ressourcengesamtstruktur
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: In den folgenden Abschnitten finden Sie Anleitungen zum Konfigurieren einer Umgebung mit mehreren Gesamtstrukturen in einem Ressourcen-/Benutzer-Gesamtstrukturmodell, um Skype for Business-Funktionen in einem Hybridszenario bereitzustellen.
ms.openlocfilehash: 2f4d0c84997dcc0d19439210e72eaf01a7a1ff26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119004"
---
# <a name="deploy-a-resource-forest-topology"></a>Bereitstellen einer Topologie mit Ressourcengesamtstruktur
 
In den folgenden Abschnitten finden Sie Anleitungen zum Konfigurieren einer Umgebung mit mehreren Gesamtstrukturen in einem Ressourcen-/Benutzer-Gesamtstrukturmodell, um Skype for Business-Funktionen in einem Hybridszenario bereitzustellen. 
  
![Umgebung mit mehreren Gesamtstrukturen für Hybrid](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>Topologieanforderungen

Es werden mehrere Benutzer gesamtstrukturen unterstützt. Denken Sie dabei an Folgendes: 
    
- Unterstützte Versionen von Lync Server und Skype for Business [](plan-hybrid-connectivity.md#server-version-requirements) Server in einer Hybridkonfiguration finden Sie unter Serverversionsanforderungen in [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md).
    
- Exchange Server können in einer oder mehreren Gesamtstrukturen bereitgestellt werden, die möglicherweise die Gesamtstruktur enthalten, die Skype for Business Server enthält. Stellen Sie sicher, dass Sie das neueste kumulative Update angewendet haben.
    
- Weitere Informationen zur Koexistenz mit Exchange Server, einschließlich Supportkriterien und Einschränkungen in verschiedenen Kombinationen von lokal und online finden Sie unter [Featureunterstützung](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) in [Plan to integrate Skype for Business and Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
    
  
## <a name="user-homing-considerations"></a>Überlegungen zur Benutzerhoming

Skype for Business-Benutzer, die lokal zuhause sind, können Exchange lokal oder online homed haben. Skype for Business #A0 sollten Exchange Online für ein optimales Erlebnis verwenden. Dies ist jedoch nicht erforderlich. Exchange lokal ist in beiden Fällen nicht erforderlich, um Skype for Business zu implementieren.
  
## <a name="configure-forest-trusts"></a>Konfigurieren von Gesamtstrukturvertrauensstellungen

In einer Ressourcen gesamtstrukturtopologie müssen die Ressourcen gesamtstrukturen, die Skype for Business Server hosten, jeder Konto gesamtstruktur vertrauen, die die Konten der Benutzer enthält, die darauf zugreifen. Wenn Sie über mehrere Benutzer gesamtstrukturübergreifende Authentifizierungen verfügen, ist es wichtig, dass das Name Suffix Routing für jede dieser Gesamtstrukturvertrauensstellungen aktiviert ist. Anweisungen finden Sie unter [Managing Forest Trusts](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772440(v=ws.11)). Wenn Sie Exchange Server in einer anderen Gesamtstruktur bereitgestellt haben und funktionen für Skype for Business-Benutzer bereitstellen, muss die Gesamtstruktur, die Exchange hostet, der Gesamtstruktur vertrauen, die Skype for Business Server hostet. Wenn z. B. Exchange in der Konto gesamtstruktur bereitgestellt würde, würde dies bedeuten, dass in dieser Konfiguration eine zweigez vertrauenswürdige Vertrauensstellung zwischen Konto- und Skype for Business-Gesamtstrukturen erforderlich ist.
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Synchronisieren von Konten mit der Gesamtstruktur, in der Skype for Business hosten

Wenn Skype for Business Server in einer Gesamtstruktur (einer Ressourcen gesamtstruktur) bereitgestellt wird, aber Benutzern in einer oder mehreren anderen Gesamtstrukturen (Konto gesamtstrukturen) Funktionen bietet, müssen Benutzer in den anderen Gesamtstrukturen als deaktivierte Benutzerobjekte in der Gesamtstruktur dargestellt werden, in der Skype for Business Server bereitgestellt wird. Ein Identitätsverwaltungsprodukt, z. B. Microsoft Identity Manager, muss bereitgestellt und konfiguriert werden, um die Benutzer aus den Konto gesamtstrukturen mit der Gesamtstruktur, in der Skype for Business Server bereitgestellt wird, bereitstellen und synchronisieren zu können. Benutzer müssen mit der Gesamtstruktur synchronisiert werden, in der Skype for Business Server als deaktivierte Benutzerobjekte hosten. Benutzer können nicht als Active Directory-Kontaktobjekte synchronisiert werden, da Azure Active Directory Connect Kontakte zur Verwendung mit Skype nicht ordnungsgemäß mit Azure AD synchronisiert.
  
Unabhängig von einer Konfiguration mit mehreren Gesamtstrukturen kann die Gesamtstruktur, die Skype for Business Server hosten, auch Funktionen für alle aktivierten Benutzer bereitstellen, die in derselben Gesamtstruktur vorhanden sind.
  
Um eine ordnungsgemäße Identitätssynchronisierung zu erhalten, müssen die folgenden Attribute synchronisiert werden: 
  
|**Benutzer gesamtstrukturen**|**Ressourcen gesamtstrukturen**|
|:-----|:-----|
|ausgewähltes Kontolinkattribut  <br/> |ausgewähltes Kontolinkattribut  <br/> |
|mail  <br/> |mail  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
Das [ausgewählte Kontolinkattribut](/azure/active-directory/hybrid/plan-connect-design-concepts) wird als Quellanker verwendet. Wenn Sie über ein anderes und unveränderliches Attribut verfügen, das Sie lieber verwenden möchten, können Sie dies tun. Achten Sie nur darauf, die AD FS-Anspruchsregel zu bearbeiten und das Attribut während der AAD Connect-Konfiguration auszuwählen.
  
Synchronisieren Sie die UPNs nicht zwischen den Gesamtstrukturen. Wir haben während der Tests festgestellt, dass wir einen eindeutigen UPN für jede Benutzer gesamtstruktur verwenden mussten, da Sie denselben UPN nicht in mehreren Gesamtstrukturen verwenden können. Daher wurden uns zwei Möglichkeiten vorgestellt, den UPN zu synchronisieren oder nicht zu synchronisieren. 
  
- Wenn der eindeutige UPN aus jeder Benutzer gesamtstruktur nicht mit dem zugeordneten deaktivierten Objekt in der Ressourcen gesamtstruktur synchronisiert wurde, würde die einmalige Anmeldung (Single Sign-On, SSO) für mindestens den ersten Anmeldeversuch unterbrochen werden (vorausgesetzt, der Benutzer hat die Option zum Speichern des Kennworts ausgewählt). Im Skype for Business-Client wird davon ausgegangen, dass die SIP/UPN-Werte identisch sind. Da die SIP-Adresse in diesem Szenario user@company.com ist, der UPN des aktivierten Objekts in der Benutzer gesamtstruktur jedoch tatsächlich user@contoso.company.com ist, würde der erste Anmeldeversuch fehlschlagen, und der Benutzer wird aufgefordert, Anmeldeinformationen ein eingeben. Nach eingabe des korrekten/tatsächlichen UPN würde die Authentifizierungsanforderung für die Domänencontroller in der Benutzer gesamtstruktur abgeschlossen, und die Anmeldung wäre erfolgreich.
    
- Wenn der eindeutige UPN aus jeder Benutzerstruktur mit dem zugeordneten deaktivierten Objekt in der Ressourcenstruktur synchronisiert wurde, würde die AD FS-Authentifizierung fehlschlagen. Die übereinstimmende Regel würde den UPN für das Objekt in der Ressourcen gesamtstruktur finden, der deaktiviert war und nicht für die Authentifizierung verwendet werden konnte. 
    
## <a name="create-a-microsoft-365-or-office-365-organization"></a>Erstellen einer Microsoft 365- oder Office 365-Organisation

Als Nächstes müssen Sie eine Microsoft 365- oder Office 365-Organisation bereitstellen, die Sie mit Ihrer Bereitstellung verwenden können. Weitere Informationen finden Sie unter [Abonnements, Lizenzen, Konten](/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)und Mandanten für die Cloudangebote von Microsoft . 
  
## <a name="configure-active-directory-federation-services"></a>Konfigurieren von Active Directory-Verbunddiensten

Sobald Sie über einen Mandanten verfügen, müssen Sie Active Directory Federation Services (AD FS) in jeder Benutzerstruktur konfigurieren. Dies setzt voraus, dass Sie über eine eindeutige SIP- und SMTP-Adresse und einen Benutzerprinzipalnamen (User Principal Name, UPN) für jede Gesamtstruktur verfügen. AD FS ist optional und wird hier verwendet, um einmaliges Anmelden (Single Sign-On, SSO) zu erhalten. DirSync mit Kennwortsynchronisierung wird ebenfalls unterstützt und kann auch an Stelle von AD FS verwendet werden. 
  
Es wurden nur Bereitstellungen mit übereinstimmenden SIP/SMTP- und UPNs getestet. Wenn keine SIP/SMTP/UPNs übereinstimmen, kann die Funktionalität eingeschränkt werden, z. B. Probleme mit der Exchange-Integration und SSO. 
  
Es sei denn, Sie verwenden einen eindeutigen SIP/SMTP/UPN für Benutzer aus jeder Gesamtstruktur, können weiterhin SSO-Probleme auftreten, unabhängig davon, wo AD FS bereitgestellt wird: 
  
- Uni-way- oder two-way-Vertrauensstellungen zwischen Ressourcen-/Benutzer-Gesamtstrukturen mit ad FS-Farm, die in jeder Benutzerstruktur bereitgestellt wird, haben alle Benutzer eine gemeinsame SIP/SMTP-Domäne, aber einen eindeutigen UPN für jede Benutzerstruktur. 
    
- Zweiwegvertrauensstellungen zwischen Ressourcen-/Benutzer-Gesamtstrukturen mit ad FS-Farm, die nur in der Ressourcenstruktur bereitgestellt wird, alle Benutzer verwenden eine gemeinsame SIP/SMTP-Domäne, aber einen eindeutigen UPN für jede Benutzerstruktur. 
    
Durch das Platzieren einer AD FS-Farm in jeder Benutzerstruktur und die Verwendung eines eindeutigen SIP/SMTP/UPN für jede Gesamtstruktur lösen wir beide Probleme. Bei Authentifizierungsversuchen würden nur die Konten in dieser bestimmten Benutzer gesamtstruktur durchsucht und übereinstimmen. Dadurch wird ein nahtloserer Authentifizierungsprozess ermöglicht. 
  
Dies ist eine Standardbereitstellung der Windows Server 2012 R2 AD FS und sollte funktionieren, bevor Sie fortfahren. Anweisungen finden Sie unter [Installieren von AD FS 2012 R2 für Microsoft 365 oder Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx). 
  
Nach der Bereitstellung müssen Sie die Anspruchsregel so bearbeiten, dass sie mit dem zuvor ausgewählten Quellanker übereinstimmen kann. Klicken Sie im AD FS MMC unter Vertrauensstellungen vertrauenden Seite mit der rechten Maustaste auf **Microsoft 365 Identity Platform** oder Microsoft Office **365 Identity Platform,** und wählen Sie dann **Anspruchsregeln** bearbeiten aus. Bearbeiten Sie die erste Regel, und ändern Sie ObjectSID in **employeeNumber**. 
  
![Bildschirm "Regeln mit mehreren Gesamtstrukturen bearbeiten"](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Konfigurieren von AAD Connect

In Ressourcen gesamtstrukturtopologien ist es erforderlich, dass Benutzerattribute aus der Ressourcen gesamtstruktur und allen Konto gesamtstrukturen mit Azure AD synchronisiert werden. Die einfachste und empfohlene Methode besteht in der Synchronisierung und  Zusammenführung von Benutzeridentitäten in Azure AD Connect aus allen Gesamtstrukturen mit aktivierten Benutzerkonten und der Gesamtstruktur, die Skype for Business enthält. Weitere Informationen finden Sie [unter Configure Azure AD Connect for Skype for Business and Teams](configure-azure-ad-connect.md).

Beachten Sie, dass AAD Connect keine lokale Synchronisierung zwischen dem Konto und den Ressourcen gesamtstrukturen bietet. Dies muss separat mithilfe von Microsoft Identity Manager oder ähnlichem Produkt konfiguriert werden, wie zuvor beschrieben.
  
Wenn Sie fertig sind und AAD Connect zusammengeführt wird, sollten Sie etwas ähnliches sehen, wenn Sie sich ein Objekt im Metaverse anschauen: 
  
![Metaverse-Objektbildschirm mit mehreren Gesamtstrukturen](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Die grün hervorgehobenen Attribute wurden aus Microsoft 365 oder Office 365 zusammengeführt, die gelben attribute wurden aus der Benutzer gesamtstruktur und das Blau aus der Ressourcen gesamtstruktur zusammengeführt. 
  
Dies ist ein Testbenutzer, und Sie können sehen, dass AAD Connect den sourceAnchor und den cloudSourceAnchor aus dem Benutzer und den Ressourcen gesamtstrukturobjekten aus Microsoft 365 oder Office 365 identifiziert hat, in unserem Fall 1101, in dem es sich um die zuvor ausgewählte employeeNumber handelt. Anschließend konnte dieses Objekt mit dem oben angezeigten zusammengeführt werden. 
  
Weitere Informationen finden Sie [unter Integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory](/azure/active-directory/hybrid/whatis-hybrid-identity). 
  
AAD Connect sollte mit den Standardwerten installiert werden, mit Ausnahme der folgenden: 
  
1. Einmaliges Anmelden – ad FS bereits bereitgestellt und funktioniert: Wählen **Sie Nicht konfigurieren aus.**
    
2. Verbinden Sie Ihre Verzeichnisse: Fügen Sie alle Domänen hinzu.
    
3. Identifizieren von Benutzern in lokalen Verzeichnissen: Wählen Sie Benutzeridentitäten **in** mehreren Verzeichnissen vorhanden aus, und wählen Sie die **Attribute ObjectSID** und **msExchangeMasterAccountSID** aus.
    
4. Identifizieren von Benutzern in Azure AD: Quellanker: Wählen Sie das Attribut aus, das Sie nach dem Lesen Auswählen eines guten [sourceAnchor-Attributs](/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute), User Principal Name - **userPrincipalName ausgewählt haben.**
    
5.  Optionale Features: Wählen Sie aus, ob Sie eine Exchange-Hybridbereitstellung haben.
    
    > [!NOTE]
    >  Wenn Sie nur über Exchange Online verfügen, kann es aufgrund der CNAME-Umleitung zu einem Problem mit #A0 während der AutoErmittlung führen. Um dies zu korrigieren, müssen Sie die Exchange-AutoErmittlungs-URL festlegen, indem Sie das folgende Cmdlet in der Skype for Business Server-Verwaltungsshell ausführen:
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  AD FS-Farm: Wählen Sie Eine vorhandene **Windows Server 2012 R2 AD FS-Farm** verwenden aus, und geben Sie den Namen des AD FS-Servers ein.
    
7.  Beenden Sie den Assistenten, und führen Sie die erforderlichen Überprüfungen aus.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>Konfigurieren der Hybridkonnektivität für Skype for Business Server

Befolgen Sie die bewährten Methoden für die Konfiguration von Skype for Business-Hybrid. Weitere Informationen finden Sie unter [Plan hybrid connectivity](plan-hybrid-connectivity.md) and Configure hybrid [connectivity](configure-hybrid-connectivity.md). 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Konfigurieren der Hybridkonnektivität für Exchange Server

Befolgen Sie bei Bedarf die bewährten Methoden für die Konfiguration von Exchange-Hybrid. Weitere Informationen finden Sie [unter Exchange Server Hybrid Deployments](/exchange/exchange-hybrid). 
