---
title: Konfigurieren einer Umgebung mit mehreren Gesamtstrukturen für hybride Skype für Unternehmen
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: Die folgenden Abschnitte enthalten Anweisungen zum Konfigurieren einer Umgebung, die mehrere Gesamtstrukturen in ein Resource-Benutzermodell-Gesamtstruktur Skype für Business-Funktionalität in einem hybridszenario bereitgestellt wurde.
ms.openlocfilehash: c07dde4db2457821a34a5419a259bfe611c3db1a
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "25030728"
---
# <a name="configure-a-multi-forest-environment-for-hybrid-skype-for-business"></a>Konfigurieren einer Umgebung mit mehreren Gesamtstrukturen für hybride Skype für Unternehmen
 
Die folgenden Abschnitte enthalten Anweisungen zum Konfigurieren einer Umgebung, die mehrere Gesamtstrukturen in ein Resource-Benutzermodell-Gesamtstruktur Skype für Business-Funktionalität in einem hybridszenario bereitgestellt wurde. 
  
![Umgebung mit mehreren Gesamtstrukturen für eine Hybridbereitstellung](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="validate-the-forest-topology"></a>Überprüfen der Topologie der Gesamtstruktur

Mehrere Benutzergesamtstrukturen werden unterstützt. Berücksichtigen Sie dabei Folgendes:   
  
- Für einen Einzelbenutzer-Gesamtstruktur oder Bereitstellung Gesamtstruktur mit mehreren Benutzern muss eine einzelne Bereitstellung von Skype für Business Server vorhanden sein.
    
- Unterstützte Versionen von Lync Server und Skype für Business Server in einer hybridkonfiguration finden Sie unter [topologieanforderungen](plan-hybrid-connectivity.md#BKMK_Topology) in [hybridkonnektivität zwischen Skype für Business Server und Office 365 planen](plan-hybrid-connectivity.md).
    
- Exchange Server kann in eine oder mehrere Gesamtstrukturen bereitgestellt werden, oder die Gesamtstruktur mit Skype für Business Server unter Umständen nicht enthalten. Stellen Sie sicher, dass Sie das neueste kumulative Update angewendet haben.
    
- Ausführliche Informationen zum Koexistenz mit Exchange Server finden Sie unter einschließlich Unterstützung Kriterien und Einschränkungen in verschiedenen Kombinationen von lokalen und online, [Feature unterstützen](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) in [Planen der Integration von Skype für Unternehmen und Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
    
Weitere Informationen finden Sie unter [System Requirements](../plan/system-requirements.md).
  
## <a name="user-homing-considerations"></a>Überlegungen zum Aufenthaltsort von Benutzern

Skype möglich für Unternehmensbenutzer lokal verwaltet Exchange lokal verwaltete oder online. Skype für Business Online-Benutzer sollten für eine optimale wünschen Exchange Online verwenden. Dies ist jedoch nicht erforderlich. Exchange lokal ist nicht erforderlich, Skype für Unternehmen in beiden Fällen zu implementieren.
  
## <a name="configure-forest-trusts"></a>Konfigurieren Sie die Gesamtstruktur-Vertrauensstellungen

Die erforderlichen Vertrauensstellungen sind bidirektionale transitive Vertrauensstellungen zwischen der Ressourcengesamtstruktur und den einzelnen Benutzergesamtstrukturen. Wenn Sie über mehrere Benutzergesamtstrukturen verfügen, ist es für die Aktivierung der gesamtstrukturübergreifenden Authentifizierung wichtig, dass für jede dieser Gesamtstruktur-Vertrauensstellungen das Namenssuffixrouting aktiviert ist. Anweisungen finden Sie unter [Verwalten von Gesamtstruktur-Vertrauensstellungen](https://technet.microsoft.com/en-us/library/cc772440.aspx). 
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Synchronisieren von Konten in der Gesamtstruktur hosten Skype für Unternehmen

Wenn Skype für Business Server in einer Gesamtstruktur (eine Ressourcengesamtstruktur) bereitgestellt wird, aber Funktionen für Benutzer in einer oder mehreren anderen Gesamtstrukturen (Konto Gesamtstrukturen) bereitstellt, müssen Benutzer in den anderen Gesamtstrukturen als deaktivierte Benutzerobjekte in der Gesamtstruktur dargestellt werden, in dem Skype für Business-Server bereitgestellt wird. Ein Identity Management-Produkt wie Microsoft Identity Manager muss bereitgestellt und konfiguriert sind, bereitstellen und synchronisieren Sie die Benutzer aus der Konto-Gesamtstrukturen in der Gesamtstruktur, in der Skype für Business Server bereitgestellt wird. Benutzer müssen in der Gesamtstruktur hosten Skype für Business Server als deaktivierte Benutzerobjekte synchronisiert werden. Benutzer können nicht als Active Directory-Kontaktobjekte und synchronisiert werden, da Azure Active Directory verbinden nicht korrekt Kontakte in Azure Active Directory für die Verwendung mit Skype synchronisiert wird.
  
Unabhängig davon keine Konfigurationen mit mehreren Gesamtstrukturen kann die Gesamtstruktur hosten Skype für Business Server auch Funktionalität für alle aktivierten Benutzer bereitstellen, die in derselben Gesamtstruktur vorhanden sind.
  
Für eine ordnungsgemäße Identitätssynchronisierung müssen die folgenden Attribute synchronisiert werden: 
  
|**Benutzergesamtstrukturen**|**Resource-Gesamtstrukturen**|
|:-----|:-----|
|Gewähltes Kontenverknüpfung-Attribut  <br/> |Gewähltes Kontenverknüpfung-Attribut  <br/> |
|mail   <br/> |mail   <br/> |
|Proxyadressen  <br/> |Proxyadressen  <br/> |
|Objekt-SID  <br/> |MsRTCSIP-OriginatorSID  <br/> |
   
Das [ausgewählte Konto Linkattribut](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/) wird als Quelle Verankerung verwendet werden. Wenn Sie einen anderen und unveränderlich Attribut, die Sie verwenden möchten vorhanden, können Sie dies tun. Seien Sie sicher, dass die Regel der AD FS-Ansprüche bearbeiten, und wählen Sie das Attribut während der Konfigurations AAD verbinden.
  
Die UPNs zwischen den Gesamtstrukturen nicht synchronisiert. Wir haben bei Tests festgestellt, dass wir einen eindeutigen UPN für jede Benutzergesamtstruktur verwenden mussten, da derselbe UPN nicht über mehrere Gesamtstrukturen verwendet werden kann. Daraus ergaben sich zwei Möglichkeiten: den UPN zu synchronisieren oder ihn nicht zu synchronisieren. 
  
-  Wenn der eindeutige UPN aus der Benutzergesamtstrukturen nicht auf das zugeordnete deaktivierte Objekt in der Ressourcengesamtstruktur synchronisiert wurde, würde einmaliges Anmelden (SSO) für mindestens aufgeteilt werden den ersten Anmeldung Versuch (vorausgesetzt, dass der Benutzer die Option Kennwort speichern ausgewählt). In der Skype für Business-Client wird davon ausgegangen, dass die SIP/UPN-Werte identisch sind. Da die SIP-Adresse in diesem Szenario user@company.com ist, der UPN des aktivierten Objekts in der Benutzergesamtstruktur aber tatsächlich user@contoso.company.com lautet, tritt beim anfänglichen Anmeldeversuch ein Fehler auf und der Benutzer wird aufgefordert, seine Anmeldeinformationen einzugeben. Nach Eingabe des korrekten/tatsächlichen UPN wird die Authentifizierungsanforderung mit den Domänencontrollern in der Benutzergesamtstruktur abgeschlossen und die Anmeldung ist erfolgreich.
    
- Wenn der eindeutige UPN aus der Benutzergesamtstrukturen mit zugeordneten deaktivierte-Objekts in der Ressourcengesamtstruktur synchronisiert wurde, würde AD FS-Authentifizierung fehl. Die entsprechende Regel findet den UPN auf dem Objekt in der Ressourcengesamtstruktur, das deaktiviert wurde und nicht für die Authentifizierung verwendet werden kann. 
    
## <a name="create-an-office-365-tenant"></a>Erstellen eines Office 365-Mandanten

Als Nächstes müssen Sie einen Office 365-Mandanten bereitstellen, der für Ihre Bereitstellung verwendet wird. Weitere Informationen finden Sie unter [Abonnements, Lizenzen, Konten, und Mandanten für Microsoft Cloud-angeboten](https://docs.microsoft.com/en-us/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings). 
  
## <a name="configure-active-directory-federation-services"></a>Konfigurieren von Active Directory-Verbunddienste

Nachdem Sie einen Mandanten haben, müssen Sie zum Konfigurieren von Active Directory-Verbunddienste (AD FS) in den einzelnen den Benutzergesamtstrukturen. Dabei wird vorausgesetzt, dass Sie eine eindeutige SIP- und SMTP-Adresse sowie einen Benutzerprinzipalnamen (UPN) für jede Gesamtstruktur haben. AD FS ist optional und wird hier einmaliges Anmelden (SSO) abgerufen. DirSync mit Kennwortsynchronisierung wird ebenfalls unterstützt und kann anstelle von AD FS verwendet werden. 
  
Es wurden nur Bereitstellungen mit übereinstimmenden SIP-/SMTP-Adressen und UPNs getestet. Über keine übereinstimmenden SIP/SMTP/UPNs kann in eingeschränkter Funktionalität, wie Probleme mit Exchange-Integration und SSO führen. 
  
Wenn Sie einen eindeutigen SIP/SMTP/UPN für Benutzer aus jeder Gesamtstruktur verwenden, können Sie weiterhin ausführen, in der SSO-Problemen, unabhängig davon, wo die AD FS bereitgestellt wird: 
  
- Uni- oder bidirektionale Vertrauensstellungen zwischen Ressourcen-/Benutzergesamtstrukturen mit einer in jeder Benutzergesamtstruktur bereitgestellten AD FS-Farm, gemeinsame SIP-/SMTP-Domäne für alle Benutzer, aber eindeutiger UPN für jede Benutzergesamtstruktur 
    
- Bidirektionale Vertrauensstellungen zwischen Ressourcen-/Benutzergesamtstrukturen mit einer nur in der Ressourcengesamtstruktur bereitgestellten AD FS-Farm, gemeinsame SIP-/SMTP-Domäne für alle Benutzer, aber eindeutiger UPN für jede Benutzergesamtstruktur 
    
Durch die Platzierung einer ADFS-Farm in jede Benutzergesamtstruktur und die Verwendung eines eindeutigen SIP-/SMTP-/UPN-Werts für jede Gesamtstruktur können wir beide Probleme beheben. Bei Authentifizierungsversuchen werden nur Konten in dieser bestimmten Benutzergesamtstruktur gesucht und zugeordnet. Damit kann ein nahtloserer Authentifizierungsprozess bereitgestellt werden. 
  
Dies wird eine Standardbereitstellung von Windows Server 2012 R2 AD FS sein, die funktionieren sollte, bevor Sie fortfahren. Anweisungen finden Sie unter [How To Install Active Directory-Verbunddienste 2012 R2 für Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx). 
  
Nach der Bereitstellung müssen Sie dann die Anspruchsregel bearbeiten, damit sie mit dem zuvor ausgewählten Quellanker übereinstimmt. In der AD FS-MMC unter Vertrauensstellungen für vertrauende Seite mit der rechten Maustaste **Identity-Plattform von Microsoft Office 365**, und klicken Sie dann auf **Edit Claim Rules**. Bearbeiten Sie die erste Regel, und ändern Sie die Objekt-SID in **Hochkommas**. 
  
![Fenster zum Bearbeiten von Regeln in mehreren Gesamtstrukturen](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Konfigurieren von AAD Connect

AAD Connect wird verwendet, um die Konten zwischen den verschiedenen Gesamtstrukturen sowie zwischen den Gesamtstrukturen und Office 365 zusammenzuführen. Sie sollten AAD Connect in der Ressourcengesamtstruktur bereitstellen. AAD Connect ist erforderlich, damit Sie mehrere Gesamtstrukturen und Office 365 synchronisieren können, was von Dirsync nicht unterstützt wird. 
  
AAD Connect führt keine Synchronisierung der Konten zwischen lokalen Gesamtstrukturen durch. AAD Connect verwendet AD-Connectors, um Objekte zu lesen, die bereits in lokalen Gesamtstrukturen synchronisiert sind (von FIM oder ähnlichen Produkten). Dann nutzt AAD Connect Filterungsregeln, um eine einzige Darstellung des übereinstimmenden aktivierten und deaktivierten Objekts im Metaverse zu erstellen, und repliziert anschließend dieses einzelne, zusammengeführte Objekt in Office 365. 
  
Wenn dieser Vorgang abgeschlossen ist und AAD Connect die Zusammenführung durchführt, sollten Sie in etwa Folgendes sehen, wenn Sie sich ein Objekt im Metaverse ansehen: 
  
![Metaverse-Objektfenster für mehrere Gesamtstrukturen](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Grünen hervorgehobenen Attribute von Office 365 zusammengeführt wurden, das Gelb aus der benutzergesamtstruktur sind und die blaue werden von der Ressourcengesamtstruktur. 
  
Dies ist ein Testbenutzer, und Sie können sehen, dass AAD verbinden die SourceAnchor und die CloudSourceAnchor vom Benutzer identifiziert wurde und die Ressource Gesamtstruktur Objekte von Office 365, in unserem Fall 1101, also die Hochkommas zuvor ausgewählt. Dieses Objekt konnte dann zu dem zusammengeführt werden, was Sie oben sehen. 
  
Weitere Informationen finden Sie unter [integrieren Ihre lokale Verzeichnisse mit Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/). 
  
Verbinden von AAD sollten unter Verwendung der Standardeinstellungen, mit Ausnahme der folgenden installiert sein: 
  
1. Einmalige Anmeldung - mit AD FS bereits bereitgestellt und Working: Wählen Sie **nicht konfigurieren**.
    
2. Verbinden Ihrer Verzeichnisse: alle Domänen hinzufügen.
    
3. Identifizieren von Benutzern in lokalen Verzeichnissen: Wählen Sie **Benutzeridentitäten über mehrere Verzeichnisse vorhanden sind**, und wählen Sie die **Objekt-SID** und **MsExchangeMasterAccountSID** Attribute.
    
4. Identifizieren von Benutzern in Azure AD: Quelle Anker: Wählen Sie das Attribut, das Sie nach dem Lesen der [Auswahl eine gute SourceAnchor-Attributs](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/), User Principal Name - **UserPrincipalName**ausgewählt haben.
    
5.  Optionale Features: Wählen Sie aus, ob Sie Exchange Hybrid bereitgestellt haben.
    
    > [!NOTE]
    >  Wenn Sie nur Exchange Online haben, kann es aufgrund der CNAME-Umleitung zu einem Problem mit OAuth-Fehlern während der AutoErmittlung kommen. Um dies zu beheben, benötigen Sie die Exchange-AutoErmittlungsdienst-URL durch Ausführen des folgenden Cmdlets aus der Skype für Business Server-Verwaltungsshell festgelegt:
  
    "Set-csoauthconfiguration" - ExchangeAutoDiscoverURL https://<span>autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    
6.  AD FS-Farm: Wählen Sie **Vorhandene Windows Server 2012 R2 AD FS-Farm verwenden** aus und geben Sie den Namen des AD FS-Servers ein.
    
7.  Schließen Sie den Assistenten ab und führen Sie die erforderlichen Überprüfungen durch.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>Konfigurieren von hybridkonnektivität für Skype Business Server

Führen Sie die bewährten Methoden für die Konfiguration von Skype für hybride Business. Weitere Informationen hierzu finden Sie unter [hybridkonnektivität planen](plan-hybrid-connectivity.md) und [Konfigurieren von hybridkonnektivität](configure-hybrid-connectivity.md). 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Konfigurieren von hybridkonnektivität für Exchange Server

Falls erforderlich, befolgen Sie die bewährten Methoden für die Konfiguration einer Exchange-Hybridbereitstellung. Weitere Informationen finden Sie unter [Hybridbereitstellungen in Exchange Server](https://technet.microsoft.com/en-us/library/jj200581%28v=exchg.150%29.aspx). 
  

