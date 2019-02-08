---
title: Exchange Unified Messaging-Migration Onlinesupport
ms.author: heidip
author: heidip
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Microsoft ist den Exchange Unified Messaging (ExchUMO) Onlinedienst vom Februar 2020 abschließen. In diesem Artikel werden zusammengefasst, was betroffen Kunden kennen und tun, um für ihre Business Continuity planen sollten.
ms.openlocfilehash: 1f755f8974ba18eba296051c547ee12b79b114d1
ms.sourcegitcommit: a80f26cdb91fac904e5c292c700b66af54261c62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2019
ms.locfileid: "29779886"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Exchange Unified Messaging-Migration Onlinesupport  

Microsoft ist den Exchange Unified Messaging (ExchUMO) Onlinedienst vom Februar 2020 Außerbetriebnehmen der als Verweis auf die [Ankündigung](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-support-for-unified-messaging-in-exchange-online/) auf 8 Februar 2019. Dieser Artikel bietet eine Zusammenfassung der was betroffenen Kunden kennen und tun, um für ihre Business Continuity planen sollten. 
 
ExchUMO wird von Kunden für Voicemail, automatische Telefonzentrale und/oder Fax Integrationsdienste bereitgestellt. Microsoft plant, damit diese Kunden zu seiner cloudbasierten Diensten migrieren, die Tausende von Kunden bereits auf Skype für Business Online und Microsoft-Teams unterstützen. 

Voicemail ist in erster Linie eine Microsoft-gesteuerte Migration. Admin eingreifen und/oder Investition möglicherweise nach einer Teilmenge von Kunden erforderlich. Automatische Telefonzentrale ist ein Administratorgesteuerte Migration. Sie müssen die vorhandenen ExchUMO automatische Telefonzentrale Strukturen in der Cloud-Telefonzentrale Cloud-Dienst neu zu erstellen. Kunden, die mit einem Drittanbieter-Nebenstellenanlage ExchUMO-Features werden in den werden nicht zu Skype Cloud Services migriert werden, da sie keine für Drittanbieter-PBX-Systeme Unterstützung. Wurde eine Stilllegung Planen von Drittanbieter-Unterstützung im Vorjahr in [diesem Blog](https://blogs.technet.microsoft.com/exchange/2017/07/18/discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging
)vorgestellt und Kunden in dieser Bereitstellungsmodell können ihre Benutzer auf eine der von Microsoft Unified Communications-Plattformen/Services migrieren oder erwerben eine Drittanbieter-Voicemail und/oder automatische Telefonzentrale Lösung für diese Benutzer. Faxintegration ist in der Cloud-basierte Services nicht unterstützt. Kunden benötigen zum Migrieren zu einer Drittanbieter-Lösung. 

### <a name="who-is-affected"></a>Wer ist betroffen?

Kunden, die eines der folgenden Features von Exchange Unified Messaging-Online-Dienst in Anspruch nehmen sind betroffen:

1. Voicemail-Dienst 
2. Automatische Telefonzentrale-Dienst 
3. Faxintegration 

> [!Note]
> Kunden, die eines der lokalen Exchange-Server mit Unified Messaging verwenden, sind nicht betroffen. 

Weitere Informationen über den Benutzer und Admin Erfahrung Auswirkung [Benutzerinteraktion Auswirkung](#user-experience-impact).

## <a name="migration-plan-overview"></a>Übersicht über die Migration planen

Microsoft hat verschiedene Kunden Deployments identifiziert, die Features von ExchUMO genutzt werden und wird basierend auf den folgenden Plan migrieren Kunden helfen werden. 


|Kundengruppe |Zeitachse  |Beschreibung  |
|---------|---------|---------|
|Kunden, die für die Migration bereit sind.<br><br>Features zum Migrieren:<br><ul><li>Voicemail</ul>   |   März – Mai 2019  |Beispiele:<ul><li>    Kunden mit Voicemail einfache Bereitstellung und Verwendung<li>Kunden, die gesamte erforderliche hergestellt für Microsoft zum Ausführen der Migrations<ul>|
|Kunden mit erforderliche Komponenten<br><br>Features zum Migrieren:<br><ul><li>Voicemail<li>Automatische Telefonzentrale</ul> |  Möglicherweise – Dezember 2019 |Beispiele: <br><ul><li>Hybridkonfiguration nicht eingerichtet/abgeschlossen<li>Hybrid-PSTN-Nummern sind nicht eingerichtet</ul>|
|Kunden, die Admin Eingreifen & Kunden Investition benötigen<br><br>Features zum Migrieren:<ul><li>Voicemail<li>Automatische Telefonzentrale<li>Faxintegration</ul>| Vom Februar 2020  | Beispiele: <br><ul><li>ExchUMO Service wird von 3. Partei PBX genutzt.<li>Kunden mit PSTN-Teilnehmerzugriff Anforderungen<li>Kunden mit SFB 2010 (wird nicht unterstützt)<li>Faxintegration</ul> |

## <a name="migration-steps"></a>Migrationsschritte

1.  **Damit Sie informiert abrufen**
 
    Machen Sie sich mit der [Ankündigung Blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-support-for-unified-messaging-in-exchange-online/) und diesem Artikel, um eine reibungslose Migration für Ihre Benutzer zu planen. Einzelheiten über die Cloud Voicemail-Funktionen finden Sie unter [Überprüfen Skype für Business Voicemail und Optionen](https://support.office.com/en-us/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) .  
 

2.  **Einrichten einer Skype für Business hybridtopologie**

    Wenn Sie keinen Skype für Business hybridtopologie eingerichtet haben, müssen Sie dafür, um eine reibungslose Migration Ihrer Voicemail-Benutzer zu aktivieren. Einzelheiten finden Sie unter [Konfigurieren von Skype für hybride Business](../hybrid/configure-federation-with-skype-for-business-online.md) . 

    > [!Note]
    > Sie müssen nicht die Benutzer an die Voicemail-Service-Migration online zu migrieren. Jedoch ist eine hybridtopologie für lokale Benutzer den Voicemail cloudbasierten Dienst verwenden können, muss festgelegt werden.

3. **Planen der automatischen Telefonzentrale-migration**
    
    Administratoren können Migrieren ihrer automatischen Telefonzentralen von ExchUMO zu Cloud-Telefonzentrale können Sie jederzeit starten. Einzelheiten finden Sie unter [Einrichten von einer Telefonzentrale Telefonsystem](../../SfbOnline/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant.md) . Microsoft plant, um zusätzliche Funktionen, die automatische Telefonzentrale bereitzustellen, die Kunden für die Migration von März 2019 kritische berücksichtigen. Administratoren sollten Features überprüfen und ihre automatische Telefonzentrale-Instanzen entsprechend migrieren. Feature-Liste Vergleich finden Sie unter der [ExchUMO und Azure featurematrix in cloudbasierten Diensten](#exchumo-and-azure-cloud-based-services-feature-matrix).

4. **Ihre Voicemail-Überprüfung nach der Migration planen und testen**

    Voicemail-Migration ist Microsoft gesteuert. Administratoren sind nicht erforderlich, keine, da die vorausgesetzte hybridtopologie hergestellt wird. Microsoft führt die erforderliche Validierung und testen, um sicherzustellen, dass der Benutzer Voicemail Migration nicht unterbrochen ist; Allerdings werden die Administratoren zum Ausführen von Tests und Validierung auf ihrer Seite aufgefordert.  Einen empfohlenen Testplan finden Sie unter [vorgeschlagene Plan und nach der Migration Überprüfung für Administratoren zu testen](#suggested-test-plan-and-post-migration-validation-for-admins) . 

    > [!Note]
    > Der Lync Server 2010 wird nicht unterstützt. Wenn Sie einen Server 2010-Bereitstellung verwenden, sollten Sie eine Server-Upgrade planen oder sollten Sie migrieren Ihrer Benutzer zu Microsoft-Teams oder Skype für Business Online.  

5. **Überwachen der Benachrichtigung-Verwaltungskonsole**

    Achten Sie für eine Benachrichtigung in der Benachrichtigung-Verwaltungskonsole mit weiteren Details und Zeitachse bezüglich Ihrer Benutzer Voicemail-Migration. Mindestens 30 Tage vor Ablauf der Migration werden Benachrichtigungen gesendet. 

    > [!Note]
    > Wenn Sie eine Benachrichtigung mit Ihrer Benutzer Migration Zeitachse erhalten und die Migration einer unternehmensbezogener Grund verschieben möchten, können Sie dazu wenden Sie sich an Microsoft Support. Beachten Sie, dass Sie die Migration über das Datum Stilllegung, Februar 2020 verschieben ist nicht möglich. Wenden Sie für Kunden, die möglicherweise weitere Fragen verfügen sich an den Kundenteam oder Microsoft Support. Kunden, die bereits mit Office 365 können eine Supportanfrage über das Office 365-Admin-Portal übermitteln. 

6. **Berücksichtigen Sie explizite beginnend Mai 2019**

    Können Sie dies bei einer frühen Voicemail-Service-Migration vom Mai 2019 (Wenn Sie eine Benachrichtigung für die Migration nicht erhalten haben), ausrichten die Migration mit einer Lizenz Annuität oder Admin-Personal Urlaubszeiten oder um unternehmensbezogener Perioden zu vermeiden. Details zu den Opt-Vorgang werden in diesem Artikel vor Mai 2019 aktualisiert werden.  

## <a name="appendix"></a>Anhang

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Featurematrix in ExchUMO und Azure cloudbasierten Diensten 




| -Dienst | Feature-Ebene | Funktion | Notizen  | Cloud VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Service-Features| Unterstützung von Drittanbietern 3rd PBX    |  | N   | J    |
| VM | Service-Features  | Unterstützt Skype für Business Server   |  | Q1CY19 | Y    |
| VM | Service-Features | Unterstützung von Microsoft-Teams|  | J | N    |
| VM | Service-Features | eDiscovery und halten  | Für Sicherheit und compliance  | Y | Y    |
| VM | Service-Features | Unterstützung für Exchange-Regeln | Für Sicherheit und compliance  | Y | Y    |
| VM | Benutzerfeatures | PSTN-Einwahl Zugriff  | Teilnehmerzugriff  | N | J    |
| VM | Benutzerfeatures | PSTN Outlook Voice Access   | Teilnehmerzugriff  | N | J    |
| VM | Benutzerfeatures | Einwahl mit einem authentifizierten Endpunkt | Aufrufen des Voicemail-Diensts zum Abhören von Voicemail-Nachrichten und Ändern von Voicemaileinstellungen| Y | Y    |
| VM | Benutzerfeatures | Benutzereinstellung zum Deaktivieren von voicemail   |  | Y | Y    |
| VM | Benutzerfeatures | Benutzer festlegen, um die persönliche Begrüßung ändern  |  | Y | Y    |
| VM | Benutzerfeatures | Benutzer, die zum Erstellen einer Ansage OOF festlegen  |  | Y | Y    |
| VM | Benutzerfeatures | So ändern Sie die Standardsprache benutzereinstellung  |  | Y | Y    |
| VM | Benutzerfeatures | Benutzer mit TTS Standard Ansage überschrieben festlegen  |  | J | N    |
| VM | Benutzerfeatures | Erfassen persönliche Begrüßung (authentifizierten Gerät) |  | Y | Y    |
| VM | Benutzerfeatures | Notieren Sie persönliche Begrüßung (PSTN) – Wiedergabe über Telefon |  | N | J    |
| VM | Benutzerfeatures | Benutzereinstellung zum Deaktivieren von Lautschrift |  | N | J    |
| VM | Benutzerfeatures | Umsetzung  |  | Y | Y    |
| VM | Benutzerfeatures | Klicken Sie auf alle Endpunkte Visual voicemail   | Unterstützt mit Benutzersteuerelement wiedergeben, Delete, Anzeige für wartende Nachrichten und Status Umschalten auf allen Endpunkten  | Y | Y    |
| VM | Benutzerfeatures | MP3-audio-Dateiformat in Outlook    |  | Y | Y    |
| VM | Benutzerfeatures | Variable Geschwindigkeit wiedergeben-Steuerelement |  | Y | Y    |
| VM | Benutzerfeatures | Eine Voicemail weiterleiten  | An andere Benutzer eine empfangene Voicemail weiterleiten | J | Y    |
| VM | Benutzerfeatures | Senden einer Sprachnachricht an eine Gruppe von Benutzern  |Voicemail-Übertragung   | N | J   |
| VM | Benutzerfeatures | Voicemail-Benachrichtigung, die mit SMS    | Benutzer können eine SMS empfangen, wenn sie eine neue Voicemail sind    | N | J    |
| VM | Benutzerfeatures | Ansage unterstützte Sprachen | Details finden Sie hier:https://docs.microsoft.com/en-us/microsoftteams/what-are-phone-system-auto-attendants | J | Y    |
| VM | Benutzerfeatures | Mailboxansageregeln |  | Q1CY19 | Y    |
| VM | Benutzerfeatures | Wiedergabe über Telefon (PSTN) – Nachricht wiedergeben | Anruf an mich auf Meine Zelle aus, um die Sprachnachricht anhören  | N | J    |
| VM | Benutzerfeatures | Wiedergabe über Telefon (Auth) - Nachricht wiedergeben | Anruf an mich auf meinem Gerät authentifizierten  | J | Y    |
| VM | Benutzerfeatures | Freigegebenes Postfach zwischen mehreren Benutzern |  | J | Y    |
| VM | Anrufer-Features  | Anrufer Erfahrung - geschützte voicemail | Anrufer kann eine Option, um eine aufgezeichnete Nachricht markieren als geschützt auswählen.| N | J    |
| VM | Anrufer-Features  | Anrufer Erfahrung - private voicemail | Anrufer kann eine Option, um eine aufgezeichnete Nachricht als privat markieren auswählen.  | N | J    |
| VM | Anrufer-Features  | Erkennung von Hintergrundgeräuschen   |  | N | J    |
| VM | Mandanten-Administrator-Features | Geschützte Voicemail auf Serverebene    | Mandanten-Administrator kann eine Regel Servicelevel, um eingehende Voicemail als geschützt zu markieren, konfigurieren. | J | Y    |
| VM | Mandanten-Administrator-Features | Änderung Aufzeichnung Dauer zeitliche Begrenzung  | CVM Festplatte und auf 5 Minuten    | N | J    |
| VM | Mandanten-Administrator-Features | Änderung Silence Erkennung timeout    |  | n/v    | Y    |
| VM | Mandanten-Administrator-Features | Ändern Sie die Nummer des Fehlers input | CVM: hartcodierte 3 | N | J    |
| VM | Mandanten-Administrator-Features | Ändern Sie die Standardsprache |  | J | Y    |
| VM | Mandanten-Administrator-Features | Aktivieren Sie Lautschrift/deaktivieren |  | J | Y    |
| VM | Mandanten-Administrator-Features | Aktivieren Sie Benachrichtigung über verpasste Anrufe/deaktivieren |  | N | J    |
| VM | Mandanten-Administrator-Features | Voicemailvorschau Verbesserung der Microsoft-Hilfe    |  | Y | Y    |
| VM | Mandanten-Administrator-Features | Anpassen der Textnachricht für aktivierte Benutzer|  | n/v    | Y    |
| VM | Mandanten-Administrator-Features | Lautschrift Gotteslästerung-Maskierung|  | J | N    |
| VM | Mandanten-Administrator-Features | Voicemail-Richtlinie    |   | Y | Y    |
| VM | Mandanten-Administrator-Features | Web-portalverwaltung   |  | CY19   | Y    |
| VM | Mandanten-Administrator-Features | PowerShell   |  | Y | Y    |
| AUTOMATISCHE TELEFONZENTRALE | Service-Features | Unterstützung von AA 3rd Party Nebenstellenanlage    |  | N | J    |
| AUTOMATISCHE TELEFONZENTRALE | Service-Features | Unterstützt Skype für Business Server   |  | Y | Y    |
| AUTOMATISCHE TELEFONZENTRALE | Service-Features | Unterstützung von Microsoft-Teams|  | J | N    |
| AUTOMATISCHE TELEFONZENTRALE | Service-Features | Wählen Sie den Namen DTMF-Eingaben    |  | Y | Y    |
| AUTOMATISCHE TELEFONZENTRALE | Service-Features | Wählen Sie den Namen Spracheingabe  |  | Y | Y    |
| AUTOMATISCHE TELEFONZENTRALE | Service-Features | Unterstützung mehrerer Sprachen | Sprache Details finden Sie hier:https://docs.microsoft.com/en-us/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| AUTOMATISCHE TELEFONZENTRALE | Service-Features | Weiterleiten Sie an Operator, CQ oder eines Benutzers |  | Y | Y    |
| AUTOMATISCHE TELEFONZENTRALE | Service-Features | Intern weiterleiten an PSTN-Nummer (RNL hat)  |  | Y | Y    |
| AUTOMATISCHE TELEFONZENTRALE | Service-Features | Weiterleiten Sie an PSTN-Nummer extern  |  | Q2CY19 | Y    |
| AUTOMATISCHE TELEFONZENTRALE | Service-Features | Geschäftszeiten |  | Y | Y    |
| AUTOMATISCHE TELEFONZENTRALE | Service-Features | Menüoptionen | IVR-Menüoptionen  | Y | Y    |
| AUTOMATISCHE TELEFONZENTRALE | Service-Features | Zuweisen einer Cloud-PSTN-Nummer zu AA |  | J | N    |
| AUTOMATISCHE TELEFONZENTRALE | Service-Features | Zuweisen einer auf Prem PSTN-Nummer zu AA  |  | Y | Y    |
| AUTOMATISCHE TELEFONZENTRALE | Service-Features | Benutzerdefinierte Benutzerauswahl  | Aktivieren der Aufrufer benutzerdefinierte Liste von Benutzern der Organisation zu erreichen| Y | Y    |
| AUTOMATISCHE TELEFONZENTRALE | Service-Features | Geschäftszeiten und Feiertage Behandlung  |  | Y | Y    |
| AUTOMATISCHE TELEFONZENTRALE | Service-Features | Benutzerdefinierte Begrüßung mit Text zu Sprachein-und-Ausgabe  |  | Y | Y    |
| AUTOMATISCHE TELEFONZENTRALE | Service-Features | Erweiterung Wählvorgang   | Einen Benutzer erreichen durch Wählen ihrer Durchwahl  | CY19   | Y    |
| AUTOMATISCHE TELEFONZENTRALE | Service-Features | Postfach für Anrufer eine Nachricht hinterlassen AA    |  | CY19   | Y    |
| AUTOMATISCHE TELEFONZENTRALE | Service-Features | Mehrere PSTN Zuweisung zu einer AA|  | Y | Y    |
| AUTOMATISCHE TELEFONZENTRALE | Mandanten-Administrator-Features | Web-portalverwaltung   |  | J | N    |
| AUTOMATISCHE TELEFONZENTRALE | Mandanten-Administrator-Features | PowerShell-cmdlets  |  | Y | Y    |
| Fax| Service-Features | Faxintegration|  | N | J    |



### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Vorgeschlagene Testplan und nach der Migration Überprüfung für Administratoren

Beim Testen der Voicemail-Funktionalität nach der Migration Ihrer Benutzer stellen Sie sicher, dass Sie die folgenden Szenarien zu berücksichtigen:

- Voicemail-Zugriff für alle Arten von Endpunkt in Ihrer Organisation überprüfen: apps und IP-Telefone. 
- Überprüfen Sie mit Beispiel-Benutzern, die den konfigurierten personalisierte Ansage für Anrufer wiedergegeben werden.   
- Wenn Ihre Organisation eine Anforderung rechtlichen oder Compliance Lautschrift für Benutzer deaktivieren verfügt, stellen Sie sicher, dass sie deaktivierte nach der Migration ist. Weitere Informationen finden Sie unter [Einrichten von Voicemail Telefonsystem](/microsoftteams/set-up-phone-system-voicemail).
- Wenn Sie bereits Exchange VM-Richtlinien und Regeln konfiguriert haben, stellen Sie sicher, dass sie wirksam werden.
- Machen Sie sich mit der Cloud Voicemail Service PowerShell-Cmdlets zum Ändern der benutzereinstellungen.  


### <a name="user-experience-impact"></a>Beeinträchtigung für die Benutzer-Erlebnis

Es folgt ein Endbenutzer Voicemail-Übersicht über die Migration wünschen.


|Erfahrung  |Ändern Sie bei der Benutzerinteraktion|
|---------|---------|
|E-Mail-Benachrichtigung | Keine Änderung<br>Für Benutzer, die über Voicemail Konto Aktivierung/Migration versendeten wird keine e-Mail gesendet. |
|Zugriff auf vorherigen Nachrichten | Keine Änderung<br>Benutzer haben Zugriff auf ihre vorherigen Voicemailnachrichten in allen unterstützten Endpunkten. |
|Empfangen von VM in Outlook SFB Apps| Keine Änderung<br>Benutzer haben weiterhin ihre Voicemail-Nachrichten in allen unterstützten Endpunkten zu empfangen. |
|Umsetzung | Erweiterte<br>CVM Lautschrift verfügt über eine viel höhere Genauigkeitsrate und unterstützten Sprachen als ExchUMO. |
|Die Einstellung für Benutzer | Neue Oberfläche<br>Benutzer werden können ihren Vorlieben von einem Benutzer die Einstellung Portal (USP) geändert. Benutzer können ihre USP über einen Hyperlink in ihre Voicemail e-Mails oder die Schaltfläche Benutzer-Einstellungen auf ihrem Client SFB zugreifen. https://aka.ms/vmsettings.   
 |Funktionen| Finden Sie in des Featuregruppe Vergleichs von Details. |
|Outlook-Regeln für VM-Nachrichten | Keine Änderung<br>Zuvor erstellte Regeln auf CVM Nachrichten nach der Migration gelten.
 |

#### <a name="user-management-and-provisioning-in-cvm"></a>Die Verwaltung und Bereitstellung in CVM 

Skype für neue Benutzer Business wird für Voicemail in CVM Service bei der Erstellung automatisch bereitgestellt werden. Bereitstellung von neuen Benutzern für Voicemail ist keine zusätzliche Admin Arbeit "oder" Lizenz erforderlich. Finden Sie Informationen zur Verwaltung von Richtlinien für bestehende und neue Benutzer [Telefonsystem Voicemail einrichten](/microsoftteams/set-up-phone-system-voicemail) .

#### <a name="admin-auto-attendant-management-experience"></a>Verwaltung der Admin-Telefonzentrale 

Finden Sie unter [Set up eine automatische Telefonzentrale Telefonsystem](../../SfbOnline/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant.md) weiterführende Informationen zur Konfiguration und Verwaltung von automatischen Telefonzentralen. 