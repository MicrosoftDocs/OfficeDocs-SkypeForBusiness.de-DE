---
title: Konfigurieren einer Umgebung mit mehreren Gesamtstrukturen für hybride Skype für Unternehmen
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/17/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 960ab8a3-352d-4b18-bc01-55b35f30ca0d
description: Die folgenden Abschnitte enthalten Anweisungen zum Konfigurieren einer Umgebung, die mehrere Gesamtstrukturen in ein Resource-Benutzermodell-Gesamtstruktur Skype für Business-Funktionalität in einem hybridszenario bereitgestellt wurde.
ms.openlocfilehash: ca3cd4bfe324690c41fbd045af967e57cab5fe36
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838563"
---
# <a name="configure-a-multi-forest-environment-for-hybrid-skype-for-business"></a>Konfigurieren einer Umgebung mit mehreren Gesamtstrukturen für hybride Skype für Unternehmen
 
Die folgenden Abschnitte enthalten Anweisungen zum Konfigurieren einer Umgebung, die mehrere Gesamtstrukturen in ein Resource-Benutzermodell-Gesamtstruktur Skype für Business-Funktionalität in einem hybridszenario bereitgestellt wurde. 
  
![Umgebung mit mehreren Gesamtstrukturen für eine Hybridbereitstellung](../../media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="validate-the-forest-topology"></a>Überprüfen der Gesamtstrukturtopologie

Mehrere Benutzergesamtstrukturen werden unterstützt. Berücksichtigen Sie dabei Folgendes:   
  
- Für eine Gesamtstruktur mit einer einzelnen Benutzer oder mehrere Gesamtstrukturen finden Sie Benutzer muss eine einzelne Bereitstellung von Skype für Business Server vorhanden sein.
    
- Unterstützte Versionen von Lync Server und Skype für Business Server in einer hybridkonfiguration finden Sie unter [topologieanforderungen](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md#BKMK_Topology) in [hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online planen](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).
    
- Exchange Server kann in eine oder mehrere Gesamtstrukturen bereitgestellt werden, oder die Gesamtstruktur mit Skype für Business Server unter Umständen nicht enthalten. Stellen Sie sicher, dass Sie das neueste kumulative Update angewendet haben.
    
- Details zur Koexistenz mit Exchange Server, einschließlich Unterstützungskriterien und Einschränkungen in verschiedenen Kombinationen aus lokaler Bereitstellung und Onlinebereitstellung, finden Sie unter [Unterstützung von Features](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) in [Plan to integrate Skype for Business and Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
    
Weitere Informationen finden Sie unter [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
  
## <a name="user-homing-considerations"></a>Überlegungen zum Aufenthaltsort von Benutzern

Skype möglich für Unternehmensbenutzer lokal verwaltet Exchange lokal verwaltete oder online. Skype für Business Online-Benutzer sollten für eine optimale wünschen Exchange Online verwenden. Dies ist jedoch nicht erforderlich. Exchange lokal ist nicht erforderlich, Skype für Unternehmen in beiden Fällen zu implementieren.
  
## <a name="configure-forest-trusts"></a>Konfigurieren von Gesamtstruktur-Vertrauensstellungen

Die erforderlichen Vertrauensstellungen sind bidirektionale transitive Vertrauensstellungen zwischen der Ressourcengesamtstruktur und den einzelnen Benutzergesamtstrukturen. Wenn Sie über mehrere Benutzergesamtstrukturen verfügen, ist es für die Aktivierung der gesamtstrukturübergreifenden Authentifizierung wichtig, dass für jede dieser Gesamtstruktur-Vertrauensstellungen das Namenssuffixrouting aktiviert ist. Anleitungen dazu finden Sie unter [Verwalten von Gesamtstruktur-Vertrauensstellungen](https://technet.microsoft.com/en-us/library/cc772440.aspx). 
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Synchronisieren von Konten in der Gesamtstruktur hosten Skype für Unternehmen

Wenn Skype für Business Server in einer Gesamtstruktur (eine Ressourcengesamtstruktur) bereitgestellt wird, aber Funktionen für Benutzer in einer oder mehreren anderen Gesamtstrukturen (Konto Gesamtstrukturen) bereitstellt, müssen Benutzer in den anderen Gesamtstrukturen als deaktivierte Benutzerobjekte in der Gesamtstruktur dargestellt werden, in dem Skype für Business-Server bereitgestellt wird. Ein Identity Management-Produkt wie Microsoft Identity Manager muss bereitgestellt und konfiguriert sind, bereitstellen und synchronisieren Sie die Benutzer aus der Konto-Gesamtstrukturen in der Gesamtstruktur, in der Skype für Business Server bereitgestellt wird. Benutzer müssen in der Gesamtstruktur hosten Skype für Business Server als deaktivierte Benutzerobjekte synchronisiert werden. Benutzer können nicht als Active Directory-Kontaktobjekte und synchronisiert werden, da Azure Active Directory verbinden nicht korrekt Kontakte in Azure Active Directory für die Verwendung mit Skype synchronisiert wird.
  
Unabhängig davon keine Konfigurationen mit mehreren Gesamtstrukturen kann die Gesamtstruktur hosten Skype für Business Server auch Funktionalität für alle aktivierten Benutzer bereitstellen, die in derselben Gesamtstruktur vorhanden sind.
  
Für eine ordnungsgemäße Identitätssynchronisierung müssen die folgenden Attribute synchronisiert werden: 
  
|**Benutzergesamtstrukturen**|**Ressourcengesamtstrukturen**|
|:-----|:-----|
|Gewähltes Kontenverknüpfung-Attribut  <br/> |Gewähltes Kontenverknüpfung-Attribut  <br/> |
|mail   <br/> |mail   <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
Das [ausgewählte Konto Linkattribut](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-design-concepts/) wird als Quelle Verankerung verwendet werden. Wenn Sie einen anderen und unveränderlich Attribut vorhanden, die Sie verwenden möchten, können Sie dazu, achten Sie die AD FS-Ansprüche Regel bearbeiten, und wählen Sie das Attribut während der Konfiguration AAD verbinden.
  
Des Benutzerprinzipalname zwischen den Gesamtstrukturen nicht synchronisiert. Wir haben bei Tests festgestellt, dass wir einen eindeutigen UPN für jede Benutzergesamtstruktur verwenden mussten, da derselbe UPN nicht über mehrere Gesamtstrukturen verwendet werden kann. Daraus ergaben sich zwei Möglichkeiten: den UPN zu synchronisieren oder ihn nicht zu synchronisieren. 
  
- Wenn der eindeutige UPN aus jeder Benutzergesamtstruktur nicht mit dem zugehörigen deaktivierten Objekt in der Ressourcengesamtstruktur synchronisiert wird, wird das einmalige Anmelden zumindest für den anfänglichen Anmeldeversuch unterbrochen (davon ausgehend, dass der Benutzer die Option zum Speichern des Kennworts ausgewählt hat). Im SfB-Client gehen wir davon aus, dass die SIP/UPN-Werte dieselben sind. Da die SIP-Adresse in diesem Szenario user@company.com ist, der UPN des aktivierten Objekts in der Benutzergesamtstruktur aber tatsächlich user@contoso.company.com lautet, tritt beim anfänglichen Anmeldeversuch ein Fehler auf und der Benutzer wird aufgefordert, seine Anmeldeinformationen einzugeben. Nach Eingabe des korrekten/tatsächlichen UPN wird die Authentifizierungsanforderung mit den Domänencontrollern in der Benutzergesamtstruktur abgeschlossen und die Anmeldung ist erfolgreich.
    
- Wenn der eindeutige UPN aus jeder Benutzergesamtstruktur mit dem zugehörigen deaktivierten Objekt in der Ressourcengesamtstruktur synchronisiert wird, tritt bei der AD FS-Authentifizierung ein Fehler auf. Die entsprechende Regel findet den UPN auf dem Objekt in der Ressourcengesamtstruktur, das deaktiviert wurde und nicht für die Authentifizierung verwendet werden kann. 
    
## <a name="create-an-office-365-tenant"></a>Erstellen eines Office 365-Mandanten

Als Nächstes müssen Sie einen Office 365-Mandanten bereitstellen, der für Ihre Bereitstellung verwendet wird. Weitere Informationen finden Sie unter [Office 365-Bereitstellungsschritte](https://social.technet.microsoft.com/wiki/contents/articles/22808.office-365-provisioning-steps.aspx). 
  
## <a name="configure-ad-fs"></a>Konfigurieren von AD FS

Nachdem ein Mandant vorhanden ist, müssen Sie die Active Directory-Verbunddienste (AD FS) in den einzelnen Benutzergesamtstrukturen konfigurieren. Dabei wird vorausgesetzt, dass Sie eine eindeutige SIP- und SMTP-Adresse sowie einen Benutzerprinzipalnamen (UPN) für jede Gesamtstruktur haben. AD FS ist optional und wird hier verwendet, um das einmalige Anmelden zu ermöglichen. DirSync mit Kennwortsynchronisierung wird ebenfalls unterstützt und kann anstelle von AD FS verwendet werden. 
  
Es wurden nur Bereitstellungen mit übereinstimmenden SIP-/SMTP-Adressen und UPNs getestet. Wenn keine übereinstimmenden SIP-/SMTP-Adressen und UPNs vorhanden sind, ist möglicherweise die Funktionalität eingeschränkt und es können beispielsweise Probleme mit der Exchange-Integration und dem einmaligen Anmelden auftreten. 
  
Wenn Sie einen eindeutigen SIP/SMTP/UPN für Benutzer aus jeder Gesamtstruktur verwenden, können Sie dennoch ausführen, einmaliges Anmelden (SSO) Probleme – unabhängig davon, wo die AD FS bereitgestellt wird: 
  
- Uni- oder bidirektionale Vertrauensstellungen zwischen Ressourcen-/Benutzergesamtstrukturen mit einer in jeder Benutzergesamtstruktur bereitgestellten AD FS-Farm, gemeinsame SIP-/SMTP-Domäne für alle Benutzer, aber eindeutiger UPN für jede Benutzergesamtstruktur 
    
- Bidirektionale Vertrauensstellungen zwischen Ressourcen-/Benutzergesamtstrukturen mit einer nur in der Ressourcengesamtstruktur bereitgestellten AD FS-Farm, gemeinsame SIP-/SMTP-Domäne für alle Benutzer, aber eindeutiger UPN für jede Benutzergesamtstruktur 
    
Durch die Platzierung einer ADFS-Farm in jede Benutzergesamtstruktur und die Verwendung eines eindeutigen SIP-/SMTP-/UPN-Werts für jede Gesamtstruktur können wir beide Probleme beheben. Bei Authentifizierungsversuchen werden nur Konten in dieser bestimmten Benutzergesamtstruktur gesucht und zugeordnet. Damit kann ein nahtloserer Authentifizierungsprozess bereitgestellt werden. 
  
Dies wird eine Standardbereitstellung von Windows Server 2012 R2 AD FS sein, die funktionieren sollte, bevor Sie fortfahren. Anweisungen finden Sie unter [So installieren Sie AD FS 2012 R2 für Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx). 
  
Nach der Bereitstellung müssen Sie dann die Anspruchsregel bearbeiten, damit sie mit dem zuvor ausgewählten Quellanker übereinstimmt. Klicken Sie in der AD FS MMC unter „Vertrauensstellungen der vertrauenden Seite“ mit der rechten Maustaste auf „Microsoft Office 365 Identity Platform“ und klicken Sie dann auf „Anspruchsregeln bearbeiten“. Bearbeiten Sie die erste Regel und ändern Sie „ObjectSID“ in „employeeNumber“. 
  
![Fenster zum Bearbeiten von Regeln in mehreren Gesamtstrukturen](../../media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Konfigurieren von AAD Connect

AAD Connect wird verwendet, um die Konten zwischen den verschiedenen Gesamtstrukturen sowie zwischen den Gesamtstrukturen und Office 365 zusammenzuführen. Sie sollten AAD Connect in der Ressourcengesamtstruktur bereitstellen. AAD Connect ist erforderlich, damit Sie mehrere Gesamtstrukturen und Office 365 synchronisieren können, was von Dirsync nicht unterstützt wird. 
  
AAD Connect führt keine Synchronisierung der Konten zwischen lokalen Gesamtstrukturen durch. AAD Connect verwendet AD-Connectors, um Objekte zu lesen, die bereits in lokalen Gesamtstrukturen synchronisiert sind (von FIM oder ähnlichen Produkten). Dann nutzt AAD Connect Filterungsregeln, um eine einzige Darstellung des übereinstimmenden aktivierten und deaktivierten Objekts im Metaverse zu erstellen, und repliziert anschließend dieses einzelne, zusammengeführte Objekt in Office 365. 
  
Wenn dieser Vorgang abgeschlossen ist und AAD Connect die Zusammenführung durchführt, sollten Sie in etwa Folgendes sehen, wenn Sie sich ein Objekt im Metaverse ansehen: 
  
![Metaverse-Objektfenster für mehrere Gesamtstrukturen](../../media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Die grün hervorgehobenen Attribute wurden von Office 365 zusammengeführt, die gelben stammen aus der Benutzergesamtstruktur und die blauen aus der Ressourcengesamtstruktur. 
  
Dies ist ein Testbenutzer und Sie können sehen, dass AAD Connect die Attribute „sourceAnchor“ und „cloudSourceAnchor“ von den Benutzer- und den Ressourcengesamtstrukturobjekten sowie von Office 365 identifiziert hat, in unserem Fall 1101, was der zuvor ausgewählten employeeNumber entspricht. Dieses Objekt konnte dann zu dem zusammengeführt werden, was Sie oben sehen. 
  
Weitere Informationen finden Sie unter [Integrieren Ihrer lokalen Identitäten in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/). 
  
AAD verbinden sollte vor allem die Standardwerte verwenden installiert werden. Mit Ausnahme der folgenden Schritte aus: 
  
1.  Einmaliges Anmelden - mit AD FS bereits bereitgestellt und arbeiten, wählen Sie nicht konfigurieren
    
2. Verbinden Ihrer Verzeichnisse – alle Domänen hinzufügen 
    
3.  Identifizieren von Benutzern in lokalen Verzeichnissen: Wählen Sie **Benutzeridentitäten über mehrere Verzeichnisse vorhanden sind** , und wählen Sie **Objekt-SID** und **MsExchangeMasterAccountSID** -Attribute
    
4. Identifizieren von Benutzern in Azure AD: Quelle Anker - wählen Sie das Attribut, das Sie nach dem Lesen der [Auswahl eine gute SourceAnchor-Attributs](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-design-concepts/)ausgewählt haben, User Principal Name - **UserPrincipalName**
    
5.  Optionale Features - wählen Sie aus, ob Sie Exchange Hybrid oder nicht bereitgestellt haben.
    
    > [!NOTE]
    >  Wenn Sie nur Exchange Online haben, kann es aufgrund der CNAME-Umleitung zu einem Problem mit OAuth-Fehlern während der AutoErmittlung kommen. Um dies zu beheben, benötigen Sie die Exchange-AutoErmittlungsdienst-URL durch Ausführen des folgenden Cmdlets aus der Skype für Business Server-Verwaltungsshell festgelegt:
  
    "Set-csoauthconfiguration" - ExchangeAutoDiscoverURLhttps://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    
6.  AD FS-Farm: Wählen Sie **Vorhandene Windows Server 2012 R2 AD FS-Farm verwenden** aus und geben Sie den Namen des AD FS-Servers ein.
    
7.  Schließen Sie den Assistenten ab und führen Sie die erforderlichen Überprüfungen durch.
    
## <a name="configure-hybrid-mode-for-skype-for-business-server"></a>Konfigurieren des Hybridmodus für Skype for Business Server

Führen Sie die bewährten Methoden für die Konfiguration von Skype für hybride Business. Weitere Informationen zur Planung finden Sie unter [Planen Ihrer hybridbereitstellung für Skype für Business Server 2015](https://technet.microsoft.com/en-us/library/jj205403.aspx)und Informationen zur Konfiguration finden Sie unter [Konfigurieren von hybridem mit Skype für Business Online](https://technet.microsoft.com/en-us/library/jj204669.aspx). 
  
## <a name="configure-hybrid-mode-for-exchange-server"></a>Konfigurieren des Hybridmodus für Exchange Server

Falls erforderlich, befolgen Sie die bewährten Methoden für die Konfiguration einer Exchange-Hybridbereitstellung. Weitere Informationen finden Sie unter [Hybridbereitstellungen in Exchange Server](https://technet.microsoft.com/en-us/library/jj200581%28v=exchg.150%29.aspx). 
  

