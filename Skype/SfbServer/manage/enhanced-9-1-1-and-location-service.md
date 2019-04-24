---
title: Verwalten von enhanced 9-1-1- und des ortungsdienstes
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype für Business Server unterstützt erweiterte 9-1-1 (E9-1-1) aufrufen in Skype für Business-Clients. Beim Konfigurieren von Skype für Business Server für E9-1-1 Angaben Notrufe Skype für Unternehmen getätigt Emergency Response Speicherort (ERL) aus der Standortinformationen-Datenbank.
ms.openlocfilehash: 31e1d529c8fb60145bc1ab4a22a75660d9f3ef63
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200302"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a>Verwalten von enhanced 9-1-1- und des ortungsdienstes in Skype für Business Server

Skype für Business Server unterstützt erweiterte 9-1-1 (E9-1-1) aufrufen in Skype für Business-Clients. Beim Konfigurieren von Skype für Business Server für E9-1-1 Angaben Notrufe Skype für Unternehmen getätigt Emergency Response Speicherort (ERL) aus der Standortinformationen-Datenbank. Verwenden Sie die Verfahren in diesem Artikel, um ortungsrichtlinie zu verwalten.

> [!Note]
> Ausführliche Informationen zum Bereitstellen von erweiterten Enterprise-VoIP-Funktionen wie E9-1-1 und den standortinformationsdienst finden Sie unter [Deploy Erweiterte Enterprise-VoIP-Funktionen](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md).

In Skype für Business Server können Sie die Standortrichtlinie Einstellungen, die sich beziehen anwenden, um erweiterte E9-1-1 (E9-1-1)-Funktionalität und speicherortseinstellungen für Benutzer oder Kontakte. Die Standortrichtlinie bestimmt, ob ein Benutzer für E9-1-1 aktiviert ist, und wenn dies der Fall ist was das Verhalten des ein Notruf ist. Beispielsweise können Sie die ortungsrichtlinie zu um definieren, welche Anzahl einen Notruf (beispielsweise 911 in den USA) ist, gibt an, ob die Sicherheit im Unternehmen automatisch benachrichtigt werden soll und wie der Anruf weitergeleitet werden sollen.

Sie können anhand von Standortrichtlinien aus der Gruppe **Netzwerkkonfiguration** in der Skype Business Server-Systemsteuerung konfigurieren. Aus der Skype Business Server-Systemsteuerung können Sie anzeigen, erstellen, ändern oder Löschen von Standortrichtlinien. Verwenden Sie das folgende Verfahren, um Informationen zu ortungsrichtlinien anzuzeigen. 


## <a name="view-location-policy-information"></a>Informationen zu ortungsrichtlinien anzeigen 

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  In der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Ortungsrichtlinie**.

4.  Wählen Sie auf der Seite **Ortungsrichtlinie** die ortungsrichtlinie, die Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.
 
    > [!NOTE]  
    > Sie können nur Informationen zu einer ortungsrichtlinie zu einem Zeitpunkt anzeigen.

Eine einzelne Richtlinie, aufgerufen, Global, kann nicht standardmäßig vorhanden und gelöscht oder umbenannt werden. Sie können jedoch die globale Richtlinie ändern. Diese Richtlinie gilt für alle Benutzer und Kontakte, es sei denn, Sie Website oder Richtlinien pro Benutzer erstellen. Richtlinien für einzelne Benutzer müssen auf bestimmte Benutzer angewendet werden.


## <a name="create-or-modify-a-location-policy"></a>Erstellen oder Ändern einer ortungsrichtlinie 

In Skype für Business Server können Sie die standardmäßige Zeitspanne zwischen Clientanforderungen für ein Location-Update aus dem Dienst Standortinformationen außer Kraft setzen. Der Standardwert beträgt 4 Stunden. Verwenden Sie das **Set-CsLocationPolicy** -Cmdlet mit dem Parameter LocationRefreshInterval, den Standardwert außer Kraft gesetzt.


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a>Erstellen Sie eine neue ortungsrichtlinie in der Skype Business Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  In der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Ortungsrichtlinie**.

4.  Klicken Sie auf der Seite **Ortungsrichtlinie** auf **neu** , und wählen Sie dann den Typ der Richtlinie, den Sie erstellen möchten:
    
      - Um eine Standortrichtlinie zu erstellen, klicken Sie auf **Standortrichtlinie**. Wählen Sie im **Dialogfeld Standort auswählen**der Website soll die Richtlinie angewendet, und klicken Sie auf **OK**. Auf der Seite **Neue Ortungsrichtlinie** das Feld **Bereich** den Wert **Website**enthält, und das Feld **Name** enthält den Namen der Website, die Sie ausgewählt haben. Sie können entweder diese Felder nicht ändern. Eine Standortrichtlinie wird automatisch auf alle Benutzer auf der angegebenen Website angewendet und überschreibt die globale Richtlinie für die Benutzer.
    
      - Klicken Sie zum Erstellen einer **Richtlinie**auf **Benutzerrichtlinie**. In der **Neuen Standortrichtlinie**enthält das Feld **Bereich** den Wert **Benutzer**. Dieser Wert kann nicht geändert werden. Geben Sie im Feld **Name** den Namen, die diese Richtlinie erhalten soll. Eine Benutzerrichtlinie gilt nicht automatisch für alle Benutzer. Nach dem Erstellen der Benutzerrichtlinie, müssen Sie die Richtlinie manuell erteilen den Benutzern oder Netzwerkstandorte, die Sie mit der Richtlinie anwenden möchten.

5.  Füllen Sie die verbleibenden Felder wie folgt aus:
    
      - **Erweiterte Notfalldienste aktivieren**   aktivieren Sie dieses Kontrollkästchen, um die für E9-1-1 dieser Richtlinie zugeordnete Benutzer zu aktivieren. Wenn notrufdienste aktiviert sind, Skype für Business Server Clients Standortinformationen für die Registrierung abruft und diese Informationen enthalten, wenn ein Notruf vorgenommen wird.
    
      - **Speicherort**   Geben Sie einen der folgenden Werte:
        
          - **Erforderliche**   der Benutzer wird aufgefordert, Standortinformationen Eingabe, wenn der Client an einem neuen Standort registriert. Der Benutzer kann die Meldung schließen, ohne Informationen einzugeben. Wenn Informationen eingegeben wird, wird ein Notruf von Anbieter für die notrufunterstützung, um den Speicherort zu überprüfen, bevor Sie an der öffentlichen Sicherheit beantworten Punkt () rettungsleitstelle (d. h., die 911 Operator) weitergeleitet wird zuerst beantwortet werden.
        
          - **Nicht erforderliche**   der Benutzer wird nicht für einen Standort aufgefordert werden. Wenn ein Anruf keine Standortinformationen erfolgt, der Anbieter Notdienste nehmen Sie den Anruf und bitten Sie für einen Standort.
        
          - **Haftungsausschluss**   diese Option ist identisch mit **erforderlich** , mit der Ausnahme, dass der Benutzer ohne Eingabe von Standortinformationen aufgefordert schließen ist nicht möglich. Der Benutzer kann immer noch einen Notruf abgeschlossen, aber keine anderen Aufrufe abgeschlossen werden können, ohne die Informationen einzugeben. Darüber hinaus wird Text des Haftungsausschlusses für den Benutzer angezeigt, die an die Folgen von Standortinformationen eingeben Ablehnung immer benachrichtigt werden können. Um den Text des Haftungsausschlusses festzulegen, müssen Sie die Skype für Business Server-Verwaltungsshell verwenden, um das Cmdlet **Set-CsLocationPolicy** oder das Cmdlet " **New-CsLocationPolicy** " mit dem Parameter EnhancedEmergencyServiceDisclaimer auszuführen. Weitere Informationen hierzu finden Sie unter [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) oder [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy).
          
    
      - **Verwenden des Speicherorts für Notdienste nur** Skype für Unternehmen kann Standortinformationen aus verschiedenen Gründen (z. B. Teamkollegen der aktuellen Position benachrichtigen) verwenden. Aktivieren Sie dieses Kontrollkästchen, um sicherzustellen, dass die Standortinformationen nur für die Verwendung mit einem Notruf verfügbar ist.
    
      - **PSTN-Verwendung**   die Öffentlichkeit switched Telephone (PSTN) Netzwerkauslastung, die verwendet wird, um zu bestimmen, welche VoIP-Route zur Weiterleitung von Notrufen von Clients, die mit diesem Profil verwendet wird. Die dieser Verwendung zugeordnete Route muss auf einen SIP-Trunk verweisen, der speziell für Notrufe eingerichtet wurde, oder auf ein ELIN (Emergency Location Identification Number)-Gateway, das den Notruf an die nächstgelegene Rettungsleitstelle weiterleitet.
    
      - **Notrufnummer**   die Nummer, die zum Erreichen der notrufdienste gewählt wird. In den USA beträgt dieser Wert 911. Die Zeichenfolge besteht aus den Ziffern 0 bis 9 bestehen und kann von 1 bis 10 Ziffern umfassen sein.
    
      - **Notrufnummer Maske**   eine Zahl, die bei der aus sie gewählt wird in den Wert der Zahlenwert Notrufnummer übersetzt werden soll. Beispielsweise wird Wenn Sie einen Wert von 212 in dieses Feld eingeben und Feld Notrufnummer hat den Wert 911, wenn ein Benutzer 212 wählt die 911 aufgerufen werden. Auf diese Weise können auch andere Notrufnummern eingerichtet werden, mit denen dennoch die Notrufdienste erreicht werden. (Dies ist beispielsweise hilfreich, wenn jemand aus einem Land oder einer Region mit einer anderen Notrufnummer versucht, die Notrufnummer des eigenen Landes zu wählen, und nicht die Notrufnummer des Landes oder der Region, in dem/der er sich gerade aufhält.) Um mehrere Notrufmasken zu definieren, trennen Sie die Werte durch ein Semikolon, z. B. 212;414. Maximale Länge der Zeichenfolge beträgt 100 Zeichen. Bei jedem Zeichen muss es sich um eine Ziffer von 0 bis 9 handeln.
      

        > [!IMPORTANT]  
        > Stellen Sie sicher, dass der Wert des angegebenen Wähleinstellungen Maske nicht als Zahl in eine orbitbereich ist. Anrufrouting Park Vorrang Notrufnummer Zeichenfolge Konvertierung. Um finden Sie unter den vorhandenen Park orbitbereiche aufrufen, klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen** , und klicken Sie dann auf **Anruf Parken**. 

    
      - **Benachrichtigung URI**   eine oder mehrere SIP-URIs Uniform Resource Identifier () benachrichtigt werden, wenn ein Notruf vorgenommen wird. Beispielsweise konnte das Unternehmen Sicherheit Office über eine Sofortnachricht benachrichtigt werden, wenn ein Notruf vorgenommen wird. Wenn dem Standort des Anrufers verfügbar ist, wird diesen Speicherort in der Benachrichtigung enthalten sein. Mehrere SIP-URIs kann als eine durch Trennzeichen getrennte Liste enthalten sein. Beispiel: „sip:security@litwareinc.com“,„sip:kmyer@litwareinc.com“. Verteilerlisten werden unterstützt. Die Zeichenfolge muss zwischen 1 und 256 Zeichen lang sein und mit dem Präfix „sip:“ beginnen. Bevor Sie im Feld URI Benachrichtigung klicken, wird ein Beispiel angezeigt.
    
      - **Konferenz-URI**   der SIP-URI in diesem Fall die Telefonnummer ein, der ein Drittanbieter, die in auf eine beliebige Notrufe per Konferenz zugeschaltet werden, die vorgenommen werden. Beispielsweise konnte das Unternehmen Sicherheit Office einen Anruf erhalten, wenn ein Notruf erfolgt und hören oder teilnehmen an dieses Aufrufs (je nach den Wert im Feld **konferenzmodus** angegeben). Die Zeichenfolge muss zwischen 1 und 256 Zeichen lang sein und mit dem Präfix „sip:“ beginnen. Ein Beispiel wird angezeigt, bis Sie in dieses Feld klicken.
    
      - **Konferenzmodus**   Wenn Sie einen Wert im Feld **Konferenz-URI** angeben, den **konferenzmodus** bestimmt, ob ein Drittanbieter an den Anruf teilnehmen können oder nur hören können. Geben Sie eine der folgenden Optionen:
        
          - **Unidirektionale**   ein dritter Teilnehmer kann die Unterhaltung zwischen dem Anrufer und der rettungsleitstelle nur hören.
        
          - **Bidirektionale**   ein Drittanbieter hören und die Unterhaltung zwischen dem Anrufer und der rettungsleitstelle teilnehmen können.

6.  Klicken Sie auf **Commit ausführen**.


    > [!IMPORTANT]  
    > Wenn Sie eine Benutzerrichtlinie erstellen, gilt zunächst die Richtlinie nicht für alle Benutzer oder Netzwerkstandorte. Wenn die Richtlinie für einen Benutzer anwenden möchten, klicken Sie in der linken Navigationsleiste auf **Benutzer** . Suchen Sie den Benutzer, die die Richtlinie angewendet werden soll. Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**. Klicken Sie auf der Seite **Server-Benutzer bearbeiten** wählen Sie die neue Standortrichtlinie aus der Dropdownliste **ortungsrichtlinie** , und klicken Sie dann auf **Commit**.<BR>Um die Richtlinie auf einen Netzwerkstandort anzuwenden, klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **Website**. Hier finden Sie den Netzwerkstandort, der die Richtlinie angewendet werden soll. Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**. **Bearbeiten der Website**wählen Sie die neue Standortrichtlinie aus der Dropdownliste **ortungsrichtlinie** , und klicken Sie dann auf **Commit**.


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a>So ändern Sie eine ortungsrichtlinie in der Skype Business Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  In der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Ortungsrichtlinie**.

4.  Wählen Sie auf der Seite **Ortungsrichtlinie** die ortungsrichtlinie, die Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Ändern Sie auf der Seite **Ortungsrichtlinie bearbeiten** die Felder nach Bedarf (Weitere Informationen hierzu finden Sie unter Schritt 5 unter "So erstellen Sie eine neue ortungsrichtlinie" weiter oben in diesem Thema).

7.  Klicken Sie auf **Commit ausführen**.

        
## <a name="delete-a-location-policy"></a>Löschen einer ortungsrichtlinie


1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  In der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Ortungsrichtlinie**.

4.  Wählen Sie auf der Seite **Ortungsrichtlinie** die ortungsrichtlinie, die Sie löschen möchten.
   
    > [!NOTE]  
    > Sie können mehr als eine Standortrichtlinie zu einem Zeitpunkt löschen. Zu diesem Zweck STRG-Taste gedrückt, und wählen Sie mehrere Richtlinien halten Sie die STRG-Taste. Oder, wenn alle Richtlinien auswählen möchten, klicken Sie auf **Alles markieren** im Menü **Bearbeiten** .


5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.

    > [!IMPORTANT]  
    > Die globale Standortrichtlinie kann nicht gelöscht werden. Wenn Sie versuchen, löschen Sie die globale Richtlinie erhalten Sie eine Warnmeldung angezeigt, und dieser Richtlinie werden auf die Standardwerte zurückgesetzt.


## <a name="see-also"></a>Siehe auch

[Erstellen oder Ändern von Netzwerkstandorten](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[Neue CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  

[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 
 
[Remove-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  

[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
