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
description: Die folgenden Abschnitte enthalten Anleitungen zum Konfigurieren einer Umgebung mit mehreren Gesamtstrukturen in einem Ressourcen-/Benutzergesamtstrukturmodell, um Skype for Business Funktionen in einem Hybridszenario bereitzustellen.
ms.openlocfilehash: 38e41a2ae845120bbdc49419d47b264f69c0a5fe
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510696"
---
# <a name="deploy-a-resource-forest-topology"></a>Bereitstellen einer Topologie mit Ressourcengesamtstruktur

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
Die folgenden Abschnitte enthalten Anleitungen zum Konfigurieren einer Umgebung mit mehreren Gesamtstrukturen in einem Ressourcen-/Benutzergesamtstrukturmodell, um Skype for Business Funktionen in einem Hybridszenario bereitzustellen. 
  
![Umgebung mit mehreren Gesamtstrukturen für Hybridbereitstellungen](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>Topologieanforderungen

Mehrere Benutzergesamtstrukturen werden unterstützt. Denken Sie dabei an Folgendes: 
    
- Unterstützte Versionen von Lync Server und Skype for Business Server in einer Hybridkonfiguration finden Sie unter [serverversion requirements](plan-hybrid-connectivity.md#server-version-requirements) in [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365.](plan-hybrid-connectivity.md)
    
- Exchange Server können in einer oder mehreren Gesamtstrukturen bereitgestellt werden, die möglicherweise die Gesamtstruktur enthalten, die Skype for Business Server enthält. Stellen Sie sicher, dass Sie das neueste kumulative Update angewendet haben.
    
- Ausführliche Informationen zum Koexistenz mit Exchange Server, einschließlich Unterstützungskriterien und Einschränkungen in verschiedenen Kombinationen von lokalen und Online-Bereitstellungen, finden Sie unter [Featureunterstützung](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) in [Plan zur Integration von Skype for Business und Exchange.](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
    
  
## <a name="user-homing-considerations"></a>Überlegungen zum Benutzer-Homing

Skype for Business lokal verwalteten Benutzer können Exchange lokal oder online verwaltet haben. Skype for Business Onlinebenutzer sollten Exchange Online für eine optimale Benutzererfahrung verwenden. Dies ist jedoch nicht erforderlich. Exchange lokal ist in beiden Fällen nicht erforderlich, um Skype for Business zu implementieren.
  
## <a name="configure-forest-trusts"></a>Konfigurieren von Gesamtstrukturvertrauensstellungen

In einer Topologie der Ressourcengesamtstruktur müssen die Ressourcengesamtstrukturen, die Skype for Business Server hosten, jeder Kontogesamtstruktur vertrauen, die Benutzerkonten enthält, die darauf zugreifen. Wenn Sie über mehrere Benutzergesamtstrukturen verfügen, ist es wichtig, dass das Namenssuffixrouting für jede dieser Gesamtstrukturvertrauensstellungen aktiviert ist, um die gesamtstrukturübergreifende Authentifizierung zu aktivieren. Anweisungen finden Sie unter [Verwalten von Gesamtstrukturvertrauensstellungen.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772440(v=ws.11)) Wenn Sie Exchange Server in einer anderen Gesamtstruktur bereitgestellt haben und funktionen für Skype for Business Benutzer bereitstellen, muss die Gesamtstruktur, die Exchange hostet, der Gesamtstruktur vertrauen, die Skype for Business Server hostet. Wenn beispielsweise Exchange in der Kontogesamtstruktur bereitgestellt werden, würde dies effektiv bedeuten, dass in dieser Konfiguration eine bidirektionale Vertrauensstellung zwischen Konto- und Skype for Business Gesamtstrukturen erforderlich ist.
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Synchronisieren von Konten in der Gesamtstruktur, die Skype for Business

Wenn Skype for Business Server in einer Gesamtstruktur (einer Ressourcengesamtstruktur) bereitgestellt wird, benutzern jedoch Funktionen in einer oder mehreren anderen Gesamtstrukturen (Kontogesamtstrukturen) bereitstellt, müssen Benutzer in den anderen Gesamtstrukturen in der Gesamtstruktur, in der Skype for Business Server bereitgestellt wird, als deaktivierte Benutzerobjekte dargestellt werden. Ein Identitätsverwaltungsprodukt, z. B. Microsoft Identity Manager, muss bereitgestellt und konfiguriert werden, um die Benutzer aus den Kontogesamtstrukturen in der Gesamtstruktur bereitzustellen und zu synchronisieren, in der Skype for Business Server bereitgestellt wird. Benutzer müssen in der Gesamtstruktur synchronisiert werden, die Skype for Business Server als deaktivierte Benutzerobjekte hostet. Benutzer können nicht als Active Directory-Kontaktobjekte synchronisiert werden, da Azure Active Directory Verbinden Kontakte für die Verwendung mit Skype nicht ordnungsgemäß mit Azure AD synchronisieren.
  
Unabhängig von einer Konfiguration mit mehreren Gesamtstrukturen kann die Gesamtstruktur, die Skype for Business Server hostet, auch Funktionen für alle aktivierten Benutzer bereitstellen, die in derselben Gesamtstruktur vorhanden sind.
  
Um eine ordnungsgemäße Identitätssynchronisierung zu erhalten, müssen die folgenden Attribute synchronisiert werden: 
  
|**Benutzergesamtstrukturen**|**Ressourcengesamtstrukturen**|
|:-----|:-----|
|Ausgewähltes Kontolinkattribut  <br/> |Ausgewähltes Kontolinkattribut  <br/> |
|mail  <br/> |mail  <br/> |
|Proxyaddresses  <br/> |Proxyaddresses  <br/> |
|Objectsid  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
Das [ausgewählte Kontoverknüpfungsattribut](/azure/active-directory/hybrid/plan-connect-design-concepts) wird als Quellanker verwendet. Wenn Sie über ein anderes und unveränderliches Attribut verfügen, das Sie lieber verwenden möchten, können Sie dies tun. Achten Sie darauf, die AD FS-Anspruchsregel zu bearbeiten und das Attribut während der AAD-Verbinden-Konfiguration auszuwählen.
  
Synchronisieren Sie die UPNs nicht zwischen den Gesamtstrukturen. Wir haben beim Testen festgestellt, dass wir einen eindeutigen UPN für jede Benutzergesamtstruktur verwenden mussten, da Sie denselben UPN nicht in mehreren Gesamtstrukturen verwenden können. Daher wurden uns zwei Möglichkeiten zur Synchronisierung des UPN oder nicht zur Synchronisierung angezeigt. 
  
- Wenn der eindeutige UPN aus jeder Benutzergesamtstruktur nicht mit dem zugeordneten deaktivierten Objekt in der Ressourcengesamtstruktur synchronisiert wurde, würde das einmalige Anmelden (Single Sign-On, SSO) für mindestens den ersten Anmeldeversuch unterbrochen (vorausgesetzt, der Benutzer hat die Option zum Speichern des Kennworts ausgewählt). Im Skype for Business-Client wird davon ausgegangen, dass die SIP-/UPN-Werte identisch sind. Da die SIP-Adresse in diesem Szenario user@company.com ist, aber der UPN des aktivierten Objekts in der Benutzergesamtstruktur tatsächlich user@contoso.company.com ist, schlägt der anfängliche Anmeldeversuch fehl, und der Benutzer wird aufgefordert, Anmeldeinformationen einzugeben. Nach der Eingabe des richtigen/tatsächlichen UPN würde die Authentifizierungsanforderung für die Domänencontroller in der Benutzergesamtstruktur abgeschlossen, und die Anmeldung wäre erfolgreich.
    
- Wenn der eindeutige UPN aus jeder Benutzergesamtstruktur mit dem zugeordneten deaktivierten Objekt in der Ressourcengesamtstruktur synchronisiert wurde, würde die AD FS-Authentifizierung fehlschlagen. Die übereinstimmungsregel suchte den UPN für das Objekt in der Ressourcengesamtstruktur, der deaktiviert wurde und nicht für die Authentifizierung verwendet werden konnte. 
    
## <a name="create-a-microsoft-365-or-office-365-organization"></a>Erstellen einer Microsoft 365 oder Office 365 Organisation

Als Nächstes müssen Sie eine Microsoft 365 oder Office 365 Organisation bereitstellen, die Sie mit Ihrer Bereitstellung verwenden können. Weitere Informationen finden Sie unter [Abonnements, Lizenzen, Konten und Mandanten für die Cloudangebote von Microsoft.](/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings) 
  
## <a name="configure-active-directory-federation-services"></a>Konfigurieren von Active Directory-Verbunddiensten

Sobald Sie über einen Mandanten verfügen, müssen Sie Active Directory-Verbunddienste (AD FS) in jeder Benutzergesamtstruktur konfigurieren. Dies setzt voraus, dass Sie über eine eindeutige SIP- und SMTP-Adresse und einen Benutzerprinzipalnamen (User Principal Name, UPN) für jede Gesamtstruktur verfügen. AD FS ist optional und wird hier verwendet, um einmaliges Anmelden (Single Sign-On, SSO) abzurufen. DirSync mit Kennwortsynchronisierung wird ebenfalls unterstützt und kann auch anstelle von AD FS verwendet werden. 
  
Es wurden nur Bereitstellungen mit übereinstimmenden SIP-/SMTP- und UPNs getestet. Wenn keine übereinstimmenden SIP-/SMTP-/UPNs vorhanden sind, kann die Funktionalität eingeschränkt sein, z. B. Probleme mit Exchange Integration und SSO. 
  
Es sei denn, Sie verwenden einen eindeutigen SIP-/SMTP-/UPN für Benutzer aus jeder Gesamtstruktur, es können weiterhin SSO-Probleme auftreten, unabhängig davon, wo AD FS bereitgestellt wird: 
  
- Unidirektionale oder bidirektionale Vertrauensstellungen zwischen Ressourcen-/Benutzergesamtstrukturen, wobei die AD FS-Farm in jeder Benutzergesamtstruktur bereitgestellt wird, teilen sich alle Benutzer eine gemeinsame SIP-/SMTP-Domäne, aber einen eindeutigen UPN für jede Benutzergesamtstruktur. 
    
- Bidirektionale Vertrauensstellungen zwischen Ressourcen-/Benutzergesamtstrukturen, bei denen die AD FS-Farm nur in der Ressourcengesamtstruktur bereitgestellt wird, teilen sich alle Benutzer eine gemeinsame SIP/SMTP-Domäne, aber einen eindeutigen UPN für jede Benutzergesamtstruktur. 
    
Durch das Platzieren einer AD FS-Farm in jeder Benutzergesamtstruktur und die Verwendung eines eindeutigen SIP/SMTP/UPN für jede Gesamtstruktur beheben wir beide Probleme. Nur die Konten in dieser bestimmten Benutzergesamtstruktur würden bei Authentifizierungsversuchen durchsucht und abgeglichen. Dadurch wird ein nahtloserer Authentifizierungsprozess ermöglicht. 
  
Dies ist eine Standardbereitstellung des Windows Server 2012 R2 AD FS und sollte vor dem Fortfahren funktionieren. Anweisungen finden Sie unter [So installieren Sie AD FS 2012 R2 Für Microsoft 365 oder Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx). 
  
Nach der Bereitstellung müssen Sie die Anspruchsregel so bearbeiten, dass sie dem zuvor ausgewählten Quellanker entspricht. Klicken Sie im AD FS MMC unter Vertrauensstellungen der vertrauenden Seite mit der rechten Maustaste auf **Microsoft 365 Identity Platform** oder Microsoft Office 365 Identity **Platform,** und wählen Sie dann **Anspruchsregeln bearbeiten** aus. Bearbeiten Sie die erste Regel, und ändern Sie ObjectSID in **employeeNumber**. 
  
![Bildschirm "Bearbeitungsregeln mit mehreren Gesamtstrukturen"](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Konfigurieren von AAD-Verbinden

In Ressourcengesamtstrukturtopologien ist es erforderlich, dass Benutzerattribute aus der Ressourcengesamtstruktur und allen Kontogesamtstrukturen in Azure AD synchronisiert werden. Die einfachste und empfohlene Vorgehensweise besteht darin, Azure AD Verbinden zu verwenden, um Benutzeridentitäten aus *allen* Gesamtstrukturen, die Benutzerkonten aktiviert haben, und der Gesamtstruktur, die Skype for Business enthält, zu synchronisieren und zusammenzuführen. Ausführliche Informationen finden Sie unter [Konfigurieren von Azure AD-Verbinden für Skype for Business und Teams.](configure-azure-ad-connect.md)

Beachten Sie, dass AAD Verbinden keine lokale Synchronisierung zwischen dem Konto und den Ressourcengesamtstrukturen bereitstellt. Dies muss separat mit Microsoft Identity Manager oder einem ähnlichen Produkt konfiguriert werden, wie weiter oben beschrieben.
  
Wenn sie fertig ist und AAD Verbinden zusammengeführt wird, sollten Sie beim Betrachten eines Objekts im Metaverse etwas ähnliches sehen: 
  
![Metaverse-Objektbildschirm mit mehreren Gesamtstrukturen](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Die grün hervorgehobenen Attribute wurden aus Microsoft 365 oder Office 365 zusammengeführt, die Gelben stammen aus der Benutzergesamtstruktur und die blau aus der Ressourcengesamtstruktur. 
  
Dies ist ein Testbenutzer, und Sie können sehen, dass AAD Verbinden die sourceAnchor- und cloudSourceAnchor-Objekte vom Benutzer und die Ressourcengesamtstrukturobjekte aus Microsoft 365 oder Office 365 identifiziert hat, in unserem Fall 1101, also der zuvor ausgewählten EmployeeNumber. Anschließend konnte dieses Objekt in dem zusammengeführt werden, was oben angezeigt wird. 
  
Weitere Informationen finden Sie unter [Integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory.](/azure/active-directory/hybrid/whatis-hybrid-identity) 
  
AAD-Verbinden sollten mithilfe der Standardwerte installiert werden, mit Ausnahme der folgenden: 
  
1. Einmaliges Anmelden – mit AD FS bereits bereitgestellt und funktioniert: Wählen Sie **"Nicht konfigurieren"** aus.
    
2. Verbinden Ihrer Verzeichnisse: Fügen Sie alle Domänen hinzu.
    
3. Identifizieren von Benutzern in lokalen **Verzeichnissen: Select User identities exist across multiple directories,** and select the **ObjectSID** and **msExchangeMasterAccountSID** attributes.
    
4. Identifizieren von Benutzern in Azure AD: Quellanker: Wählen Sie das Attribut aus, das Sie nach dem Lesen [eines guten sourceAnchor-Attributs](/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute)ausgewählt haben, Benutzerprinzipalname - **userPrincipalName**.
    
5.  Optionale Features: Wählen Sie aus, ob Sie Exchange Hybrid bereitgestellt haben.
    
    > [!NOTE]
    >  Wenn Sie nur Exchange Online haben, kann ein Problem mit OAuth-Fehlern während der AutoErmittlung aufgrund der CNAME-Umleitung auftreten. Um dies zu beheben, müssen Sie die Exchange AutoErmittlungs-URL festlegen, indem Sie das folgende Cmdlet aus der Skype for Business Server Verwaltungsshell ausführen:
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  AD FS-Farm: Wählen Sie **eine vorhandene Windows Server 2012 R2 AD FS-Farm** verwenden aus, und geben Sie den Namen des AD FS-Servers ein.
    
7.  Schließen Sie den Assistenten ab, und führen Sie die erforderlichen Überprüfungen durch.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>Konfigurieren der Hybridkonnektivität für Skype for Business Server

Befolgen Sie die bewährten Methoden zum Konfigurieren Skype for Business Hybrid. Weitere Informationen finden Sie unter Planen der [Hybridkonnektivität](plan-hybrid-connectivity.md) und [Konfigurieren der Hybridkonnektivität.](configure-hybrid-connectivity.md) 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Konfigurieren der Hybridkonnektivität für Exchange Server

Befolgen Sie bei Bedarf die bewährten Methoden zum Konfigurieren Exchange Hybrid. Weitere Informationen finden Sie unter [Exchange Server Hybridbereitstellungen.](/exchange/exchange-hybrid) 
