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
description: Die folgenden Abschnitte enthalten Anleitungen zum Konfigurieren einer Umgebung mit mehreren Gesamtstrukturen in einem Ressourcen-Benutzer-Gesamtstrukturmodell, um Skype for Business Funktionalität in einem Hybrid Szenario bereitzustellen.
ms.openlocfilehash: acfca3b29407b019b87f5429906dbc72b4ef7dc3
ms.sourcegitcommit: 0835f4335ebc8ca53b8348e0b1b906828eb4e13e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "43918684"
---
# <a name="deploy-a-resource-forest-topology"></a>Bereitstellen einer Topologie mit Ressourcengesamtstruktur
 
Die folgenden Abschnitte enthalten Anleitungen zum Konfigurieren einer Umgebung mit mehreren Gesamtstrukturen in einem Ressourcen-Benutzer-Gesamtstrukturmodell, um Skype for Business Funktionalität in einem Hybrid Szenario bereitzustellen. 
  
![Multi-Forest-Umgebung für Hybrid](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>Topologieanforderungen

Mehrere Benutzergesamtstrukturen werden unterstützt. Denken Sie dabei an Folgendes: 
    
- Informationen zu unterstützten Versionen von lync Server und Skype for Business Server in einer Hybrid Konfiguration finden Sie unter [Server Versionsanforderungen](plan-hybrid-connectivity.md#server-version-requirements) in [Plan Hybrid Connectivity zwischen Skype for Business Server und Office 365](plan-hybrid-connectivity.md).
    
- Exchange Server können in einer oder mehreren Gesamtstrukturen bereitgestellt werden, die möglicherweise die Gesamtstruktur enthalten, die Skype for Business Server enthält. Stellen Sie sicher, dass Sie das neueste kumulative Update angewendet haben.
    
- Ausführliche Informationen zur Koexistenz mit Exchange Server, einschließlich Support Kriterien und Einschränkungen in verschiedenen Kombinationen von lokal und Online, finden Sie unter [Feature Support](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) in [Plan to Integration Skype for Business and Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
    
  
## <a name="user-homing-considerations"></a>Überlegungen zur Benutzer Referenzierung

Skype for Business lokal verwalteten Benutzer können Exchange lokal oder online bereit haben. Skype for Business Online Benutzer sollten Exchange Online verwenden, um eine optimale Oberfläche zu erzielen. Dies ist jedoch nicht erforderlich. Exchange lokal ist nicht erforderlich, um Skype for Business in beiden Fällen zu implementieren.
  
## <a name="configure-forest-trusts"></a>Konfigurieren von Gesamtstrukturvertrauensstellungen

In einer Topologie mit Ressourcengesamtstruktur müssen die Ressourcengesamtstrukturen, die Skype for Business Server hosten, jeder Kontogesamtstruktur, die Benutzerkonten enthält, die darauf zugreifen sollen, Vertrauen. Wenn Sie über mehrere Benutzergesamtstrukturen verfügen, ist es wichtig, dass die namens Suffix-Weiterleitung für jede dieser Gesamtstrukturvertrauensstellungen aktiviert ist, um die gesamtstrukturübergreifende Authentifizierung zu aktivieren. Anweisungen finden Sie unter [Verwalten von Gesamtstruktur-Vertrauensstellungen](https://technet.microsoft.com/library/cc772440.aspx). Wenn Sie Exchange Server in einer anderen Gesamtstruktur bereitgestellt haben und diese Funktionalität für Skype for Business Benutzer bereitstellt, muss die Gesamtstruktur, die Exchange hostet, dem Gesamtstruktur Hosting Skype for Business Server Vertrauen. Wenn beispielsweise Exchange in der Kontogesamtstruktur bereitgestellt wurde, bedeutet dies effektiv eine bidirektionale Vertrauensstellung zwischen dem Konto, und Skype for Business Gesamtstrukturen sind in dieser Konfiguration erforderlich.
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Synchronisieren von Konten in der Gesamtstruktur-Host Skype for Business

Wenn Skype for Business Server in einer Gesamtstruktur (einer Ressourcengesamtstruktur) bereitgestellt wird, aber Benutzern in einer oder mehreren Gesamtstrukturen (Konto Gesamtstrukturen) Funktionen bereitstellt, müssen Benutzer in den anderen Gesamtstrukturen als deaktivierte Benutzerobjekte in der Gesamtstruktur dargestellt werden, in der Skype for Business Server bereitgestellt wird. Ein Identitäts Verwaltungsprodukt wie Microsoft Identity Manager muss bereitgestellt und konfiguriert werden, um die Benutzer aus den Konto Gesamtstrukturen in der Gesamtstruktur bereitzustellen und zu synchronisieren, in der Skype for Business Server bereitgestellt wird. Benutzer müssen mit der Gesamtstruktur synchronisiert werden, die Skype for Business Server als deaktivierte Benutzerobjekte hostet. Benutzer können nicht als Active Directory Kontaktobjekte synchronisiert werden, da Azure Active Directory Connect Kontakte mit Azure AD nicht ordnungsgemäß für die Verwendung mit Skype synchronisiert.
  
Unabhängig von der Konfiguration mit mehreren Gesamtstrukturen kann die Gesamtstruktur-Host Skype for Business Server auch Funktionen für alle aktivierten Benutzer bereitstellen, die in der gleichen Gesamtstruktur vorhanden sind.
  
Um eine ordnungsgemäße Identitätssynchronisierung zu erhalten, müssen die folgenden Attribute synchronisiert werden: 
  
|**Benutzergesamtstrukturen**|**Ressourcengesamtstrukturen**|
|:-----|:-----|
|Ausgewähltes Konto Link Attribut  <br/> |Ausgewähltes Konto Link Attribut  <br/> |
|mail  <br/> |mail  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
Das [ausgewählte Konto Link Attribut](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts) wird als Quellanker verwendet. Wenn Sie ein anderes und unveränderliches Attribut haben, das Sie lieber verwenden möchten, können Sie dies tun; Achten Sie darauf, die AD FS-Forderungs Regel zu bearbeiten und das Attribut während der Aad Connect-Konfiguration auszuwählen.
  
Synchronisieren Sie die UPNs nicht zwischen den Gesamtstrukturen. Wir haben beim Testen festgestellt, dass für jede Benutzergesamtstruktur ein eindeutiger UPN verwendet werden musste, da Sie nicht den gleichen UPN in mehreren Gesamtstrukturen verwenden können. Dadurch wurden zwei Möglichkeiten angezeigt, um den UPN zu synchronisieren oder nicht zu synchronisieren. 
  
- Wenn der eindeutige UPN aus jeder Benutzergesamtstruktur nicht mit dem zugeordneten deaktivierten Objekt in der Ressourcengesamtstruktur synchronisiert wurde, würde das einmalige Anmelden (Single Sign-on, SSO) mindestens für den anfänglichen Anmeldeversuch unterbrochen (vorausgesetzt, der Benutzer hat die Option zum Speichern des Kennworts ausgewählt). Im Skype for Business-Client wird davon ausgegangen, dass die SIP/UPN-Werte identisch sind. Da die SIP-Adresse in diesem Szenario User@Company.com ist, aber der UPN des aktivierten Objekts in der Benutzergesamtstruktur tatsächlich user@contoso.Company.com ist, schlägt der anfängliche Anmeldeversuch fehl, und der Benutzer wird aufgefordert, Anmeldeinformationen einzugeben. Bei der Eingabe Ihres richtigen/tatsächlichen UPN würde die Authentifizierungsanforderung für die Domänencontroller in der Benutzergesamtstruktur abgeschlossen werden, und die Anmeldung würde erfolgreich sein.
    
- Wenn der eindeutige UPN aus jeder Benutzergesamtstruktur mit dem zugeordneten deaktivierten Objekt in der Ressourcengesamtstruktur synchronisiert wurde, tritt bei der AD FS-Authentifizierung ein Fehler auf. Die Übereinstimmungsregel würde den UPN für das Objekt in der Ressourcengesamtstruktur finden, das deaktiviert war und nicht für die Authentifizierung verwendet werden konnte. 
    
## <a name="create-an-office-365-organization"></a>Erstellen einer Office 365 Organisation

Als nächstes müssen Sie eine Office 365 Organisation bereitstellen, die mit Ihrer Bereitstellung verwendet werden soll. Weitere Informationen finden Sie unter [Abonnements, Lizenzen, Konten und Mandanten für die Cloud-Angebote von Microsoft](https://docs.microsoft.com/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings). 
  
## <a name="configure-active-directory-federation-services"></a>Konfigurieren von Active Directory Verbunddiensten

Nachdem Sie einen Mandanten haben, müssen Sie Active Directory Verbunddienste (AD FS) in allen Benutzergesamtstrukturen konfigurieren. Dabei wird davon ausgegangen, dass Sie über eine eindeutige SIP-und SMTP-Adresse und einen Benutzerprinzipalnamen (UPN) für jede Gesamtstruktur verfügen. AD FS ist optional und wird hier verwendet, um einmaliges Anmelden (Single Sign-on, SSO) zu erhalten. Dirsync mit Kennwortsynchronisierung wird ebenfalls unterstützt und kann auch anstelle von AD FS verwendet werden. 
  
Es wurden nur Bereitstellungen mit übereinstimmenden SIP/SMTP-und UPNs getestet. Die Übereinstimmung mit SIP/SMTP/UPNs kann zu einer eingeschränkten Funktionalität führen, beispielsweise bei Problemen mit der Exchange-Integration und SSO. 
  
Wenn Sie keinen eindeutigen SIP/SMTP/UPN für Benutzer aus jeder Gesamtstruktur verwenden, können Sie immer noch bei SSO-Problemen ausgeführt werden, unabhängig davon, wo AD FS bereitgestellt wird: 
  
- Unidirektionale oder bidirektionale Vertrauensstellungen zwischen Ressourcen-und Benutzergesamtstrukturen mit AD FS-Farm, die in jeder Benutzergesamtstruktur bereitgestellt wird, verwenden alle Benutzer eine gemeinsame SIP/SMTP-Domäne, jedoch einen eindeutigen UPN für jede Benutzergesamtstruktur. 
    
- Bidirektionale Vertrauensstellungen zwischen Ressourcen-und Benutzergesamtstrukturen mit AD FS-Farm, die nur in der Ressourcengesamtstruktur bereitgestellt wird, verwenden alle Benutzer eine gemeinsame SIP/SMTP-Domäne, jedoch einen eindeutigen UPN für jede Benutzergesamtstruktur. 
    
Durch das Platzieren einer AD FS-Farm in jeder Benutzergesamtstruktur und der Verwendung eines eindeutigen SIP/SMTP/UPN für jede Gesamtstruktur lösen wir beide Probleme. Nur die Konten in dieser bestimmten Benutzergesamtstruktur werden bei Authentifizierungsversuchen durchsucht und abgeglichen. Dadurch wird ein nahtloser Authentifizierungsprozess gewährleistet. 
  
Dies ist eine Standardbereitstellung des Windows Server 2012 R2 AD FS und sollte funktionieren, bevor Sie fortfahren. Anweisungen finden Sie unter [Vorgehensweise zum Installieren von AD FS 2012 R2 für Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx). 
  
Nachdem Sie bereitgestellt wurden, müssen Sie die Forderungs Regel so bearbeiten, dass Sie dem zuvor ausgewählten Quellanker entspricht. Klicken Sie in der AD FS-MMC unter Vertrauensstellungen der vertrauenden Seite mit der rechten Maustaste auf **Microsoft Office 365-Identitäts Plattform**, und klicken Sie dann auf **Anspruchsregeln bearbeiten**. Bearbeiten Sie die erste Regel, und ändern Sie die Objekte in **employeeNumber**. 
  
![Bildschirm mit Bearbeitungsregeln für mehrere Gesamtstrukturen](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Konfigurieren von Aad Connect

In Ressourcengesamtstruktur-Topologien ist es erforderlich, dass Benutzerattribute sowohl aus der Ressourcengesamtstruktur als auch aus beliebigen Konto Gesamtstrukturen in Azure AD synchronisiert werden. Die einfachste und empfohlene Vorgehensweise besteht darin, dass Azure AD Connect-Benutzeridentitäten aus *allen* Gesamtstrukturen mit aktivierten Benutzerkonten und der Gesamtstruktur, die Skype for Business enthält, synchronisieren und zusammenführen. Ausführliche Informationen finden Sie unter [Konfigurieren Azure AD Connect für Skype for Business und Teams](configure-azure-ad-connect.md).

Beachten Sie, dass Aad Connect keine Synchronisierung lokal zwischen dem Konto und den Ressourcengesamtstrukturen bereitstellt. Das muss wie zuvor beschrieben mit Microsoft Identity Manager oder einem ähnlichen Produkt separat konfiguriert werden.
  
Wenn Sie fertig sind und Aad Connect zusammengeführt wird, sollten Sie, wenn Sie sich ein Objekt in der Metaverse ansehen, etwas Ähnliches sehen: 
  
![Multi-Forest-Metaverse-Objekt Bildschirm](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Die grün markierten Attribute wurden aus Office 365 zusammengeführt, die gelben stammen aus der Benutzergesamtstruktur und die blau aus der Ressourcengesamtstruktur. 
  
Dies ist ein Testbenutzer, und Sie können sehen, dass Aad Connect die Attributs und die cloudSourceAnchor von den Objekten User und Resource Forest aus Office 365 identifiziert hat, in unserem Fall 1101, dem zuvor ausgewählten employeeNumber. Es war dann in der Lage, dieses Objekt in das zu verschmelzen, was Sie oben sehen. 
  
Weitere Informationen finden Sie unter [integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/). 
  
Aad Connect sollte mit den Standardeinstellungen installiert werden, mit Ausnahme der folgenden: 
  
1. Einmaliges Anmelden – mit AD FS bereits bereitgestellt und funktioniert: Wählen Sie **nicht konfigurieren**aus.
    
2. Verbinden Sie Ihre Verzeichnisse: Fügen Sie alle Domänen hinzu.
    
3. Identifizieren von Benutzern in lokalen Verzeichnissen: Wählen Sie **Benutzeridentitäten in mehreren Verzeichnissen**aus, und wählen Sie die Attribute **Objekt** -und **msexchangemasteraccount sid aus** .
    
4. Identifizieren von Benutzern in Azure AD: Quellanker: Wählen Sie das Attribut aus, das Sie nach dem Lesen ausgewählt haben, [indem Sie ein gutes Attributs-Attribut](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute), den Benutzerprinzipalnamen – **userPrincipalName**.
    
5.  Optionale Features: Wählen Sie aus, ob Exchange-hybridbereitstellung bereitgestellt ist.
    
    > [!NOTE]
    >  Wenn Sie nur Exchange Online haben, könnte ein Problem mit OAuth-Fehlern während der AutoErmittlung aufgrund der CNAME-Umleitung auftreten. Um dies zu beheben, müssen Sie die Exchange-Auto Ermittlungs-URL festlegen, indem Sie das folgende Cmdlet aus der Skype for Business Server Verwaltungsshell ausführen:
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  AD FS-Farm: Wählen Sie **vorhandene Windows Server 2012 R2 AD FS-Farm verwenden** aus, und geben Sie den Namen des AD FS-Servers ein.
    
7.  Beenden Sie den Assistenten, und führen Sie die erforderlichen Validierungen aus.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>Konfigurieren der Hybrid Konnektivität für Skype for Business Server

Befolgten Sie die bewährten Methoden für die Konfiguration Skype for Business Hybrid. Weitere Informationen finden Sie unter [Plan Hybrid Connectivity](plan-hybrid-connectivity.md) and [configure Hybrid Connectivity](configure-hybrid-connectivity.md). 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Konfigurieren der Hybrid Konnektivität für Exchange Server

Führen Sie bei Bedarf die bewährten Methoden zum Konfigurieren der Exchange-hybridbereitstellung aus. Weitere Informationen finden Sie unter [Exchange Server Hybrid Bereitstellungen](https://docs.microsoft.com/exchange/exchange-hybrid). 
  
