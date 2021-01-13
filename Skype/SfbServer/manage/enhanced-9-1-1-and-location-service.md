---
title: Verwalten der erweiterten 9-1-1-Dienste und des Standortdiensts
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server unterstützt E9-1-1-Anrufe (erweitert) von Skype for Business-Clients. Wenn Sie Skype for Business Server für E9-1-1 konfigurieren, enthalten Notrufe, die von Skype for Business aus ausgeführt werden, Informationen zum Standortinformationsdienst (Emergency Response Location, ERL) aus der Standortinformationsdienstdatenbank.
ms.openlocfilehash: c5b626763de78495a2feaa5ecb1ba77e367bd77d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817475"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a>Verwalten der erweiterten 9-1-1 und des Standortdiensts in Skype for Busines Server

Skype for Business Server unterstützt anrufe mit erweiterten 9-1-1 (E9-1-1) von Skype for Business-Clients. Wenn Sie Skype for Business Server für E9-1-1 konfigurieren, enthalten Notrufe, die von Skype for Business aus ausgeführt werden, Informationen zum Notfallstandort (Emergency Response Location, ERL) aus der Standortinformationsdienstdatenbank. Verwenden Sie die Verfahren in diesem Artikel zum Verwalten von Standortrichtlinien.

> [!Note]
> Weitere Informationen zur Bereitstellung erweiterter Enterprise-VoIP, z. B. E9-1-1 und des Standortinformationsdiensts, finden Sie unter [Deploy advanced Enterprise-VoIP features](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md).

In Skype for Business Server können Sie die Standortrichtlinie verwenden, um Einstellungen im Zusammenhang mit der Erweiterten 9-1-1-Funktion (E9-1-1) und standorteinstellungen für Benutzer oder Kontakte anzuwenden. Die Standortrichtlinie bestimmt, ob ein Benutzer für E9-1-1 aktiviert ist und ob das Verhalten eines Notrufs ist. Sie können z. B. mithilfe der Standortrichtlinie definieren, welche Nummer einen Notruf (z. B. 911 in den USA) bildet, ob die Unternehmenssicherheit automatisch benachrichtigt werden soll und wie der Anruf geroutet werden soll.

Sie können Standortrichtlinien  in der Netzwerkkonfigurationsgruppe in der Skype for Business Server-Systemsteuerung konfigurieren. In der Skype for Business Server-Systemsteuerung können Sie Standortrichtlinien anzeigen, erstellen, ändern oder löschen. Verwenden Sie das folgende Verfahren, um Informationen zu Ortungsrichtlinien anzuzeigen. 


## <a name="view-location-policy-information"></a>Anzeigen von Standortrichtlinieninformationen 

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Standortrichtlinie".**

4.  Klicken Sie auf der Seite **Ortungsrichtlinie** auf die Ortungsrichtlinie, die geändert werden soll.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.
 
    > [!NOTE]  
    > Sie können jeweils nur Informationen zu einer Ortungsrichtlinie anzeigen.

Standardmäßig ist eine einzige Richtlinie (Global) vorhanden, die nicht gelöscht oder umbenannt werden kann. Sie können die globale Richtlinie jedoch ändern. Sofern keine Standortrichtlinien oder Richtlinien auf Benutzerbasis erstellt werden, wird diese Richtlinie auf sämtliche Benutzer und Kontakte angewendet. Richtlinien auf Benutzerbasis müssen auf bestimmte Benutzer angewendet werden.


## <a name="create-or-modify-a-location-policy"></a>Erstellen oder Ändern einer Standortrichtlinie 

In Skype for Business Server können Sie die Standardzeit zwischen Clientanforderungen für eine Standortaktualisierung vom Standortinformationsdienst außer Kraft setzen. Der Standardwert ist 4 Stunden. Verwenden Sie **das Cmdlet "Set-CsLocationPolicy"** mit dem Parameter "LocationRefreshInterval", um den Standardwert außer Kraft zu setzen.


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a>So erstellen Sie eine neue Standortrichtlinie in der Skype for Business Server-Systemsteuerung

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Standortrichtlinie".**

4.  Klicken Sie **auf der** Seite "Standortrichtlinie" auf **"Neu",** und wählen Sie dann den Typ der Richtlinie aus, die Sie erstellen möchten:
    
      - Klicken Sie auf "Standortrichtlinie", um eine **Standortrichtlinie zu erstellen.** Wählen **Sie in "Standort auswählen"** den Standort aus, auf den die Richtlinie angewendet werden soll, und klicken Sie auf **"OK".** Auf der **Seite "Neue Standortrichtlinie"** enthält das Feld "Bereich" den Wert **"Site",** und das Feld **"Name"** enthält den Namen des standorts, den Sie ausgewählt haben.  Sie können keines dieser Felder ändern. Eine Standortrichtlinie wird automatisch auf alle Benutzer am angegebenen Standort angewendet und setzt die globale Richtlinie für diese Benutzer außer Kraft.
    
      - Klicken Sie auf **Benutzerrichtlinie, um** eine **Benutzerrichtlinie zu erstellen.** In the **New Location Policy,** the **Scope** field contains the value **User**. Sie können diesen Wert nicht ändern. Geben Sie **im Feld "Name"** den Namen ein, den Sie dieser Richtlinie geben möchten. Eine Benutzerrichtlinie gilt nicht automatisch für Benutzer. Nach dem Erstellen der Benutzerrichtlinie müssen Sie die Richtlinie manuell den Benutzern oder Netzwerkstandorten erteilen, auf die Sie die Richtlinie anwenden möchten.

5.  Füllen Sie die verbleibenden Felder wie folgt aus:
    
      - **Aktivieren erweiterter Notrufdienste**   Aktivieren Sie dieses Kontrollkästchen, um die dieser Richtlinie zugeordneten Benutzer für E9-1-1 zu aktivieren. Wenn die Notrufdienste aktiviert sind, rufen Skype for Business Server-Clients Standortinformationen zur Registrierung ab und schließen diese Informationen ein, wenn ein Notruf erfolgt.
    
      - **Position**   Geben Sie einen der folgenden Werte an:
        
          - **Erforderlich**   Der Benutzer wird zur Eingabe von Standortinformationen aufgefordert, wenn sich der Client an einem neuen Speicherort registriert. Der Benutzer kann die Eingabeaufforderung ohne Eingabe von Informationen verwerfen. Wenn Informationen eingegeben werden, wird zunächst ein Notruf vom Anbieter der Notrufdienste beantwortet, um den Standort zu überprüfen, bevor er an die Rettungsstelle (Public Safety Answering Point, PSAP) (d. h. die Rettungsstelle 911) geroutet wird.
        
          - **Nicht erforderlich**   Der Benutzer wird nicht zur Eingabe eines Standorts aufgefordert. Wenn ein Anruf ohne Standortinformationen erfolgt, wird der Notruf vom Anbieter der Notrufdienste beantwortet und nach einem Standort gefragt.
        
          - **Haftungsausschluss**   Diese Option ist identisch mit **"Erforderlich",** außer dass der Benutzer die Eingabeaufforderung nicht ohne Eingabe von Standortinformationen schließen kann. Der Benutzer kann weiterhin einen Notruf abschließen, aber keine weiteren Anrufe können ohne Eingabe der Informationen durchgeführt werden. Darüber hinaus wird dem Benutzer ein Haftungsausschlusstext angezeigt, der den Benutzer vor den Folgen der Zurückung der Eingabe von Standortinformationen warnen kann. Zum Festlegen des Haftungsausschlusstexts müssen Sie die Skype for Business Server-Verwaltungsshell verwenden, um das **Cmdlet "Set-CsLocationPolicy"** oder das Cmdlet **"New-CsLocationPolicy"** mit dem Parameter "EnhancedEmergencyServiceDisclaimer" ausführen zu können. Weitere Informationen finden Sie unter [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) oder [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy).
          
    
      - **Standort nur für Notrufdienste verwenden** Skype for Business kann Standortinformationen aus verschiedenen Gründen verwenden (z. B. um Teamkollegen über Ihren aktuellen Standort zu benachrichtigen). Aktivieren Sie dieses Kontrollkästchen, um sicherzustellen, dass Standortinformationen nur für die Verwendung mit einem Notruf verfügbar sind.
    
      - **PstN-Verwendung**   Die Verwendung des Telefonnetzes (Public Switched Telephone Network, PSTN), die verwendet wird, um zu bestimmen, welche Sprachroute zum Routen von Notrufen von Clients verwendet wird, die dieses Profil verwenden. Die dieser Verwendung zugeordnete Route muss auf einen SIP-Trunk verweisen, der speziell für Notrufe eingerichtet wurde, oder auf ein ELIN (Emergency Location Identification Number)-Gateway, das den Notruf an die nächstgelegene Rettungsleitstelle weiterleitet.
    
      - **Notrufnummer**   Die Nummer, die zum Erreichen der Notrufdienste gewählt wird. In den USA lautet dieser Wert "911". Die Zeichenfolge muss aus den Ziffern 0 bis 9 bestehen und kann 1 bis 10 Ziffern umfassen.
    
      - **Notrufwählmaske**   Eine Nummer, die Sie in den Wert der Notrufnummer übersetzen möchten, wenn sie gewählt wird. Wenn Sie z. B. den Wert 212 in dieses Feld eingeben und das Feld für notrufnummer den Wert 911 hat, wird der Anruf an 911 vorgenommen, wenn ein Benutzer die Nummer 212 wählt. Auf diese Weise können auch andere Notrufnummern eingerichtet werden, mit denen dennoch die Notrufdienste erreicht werden. (Dies ist beispielsweise hilfreich, wenn jemand aus einem Land oder einer Region mit einer anderen Notrufnummer versucht, die Notrufnummer des eigenen Lands zu wählen, und nicht die Notrufnummer des Lands oder der Region, in dem/der er sich gerade aufhält.) Um mehrere Notrufmasken zu definieren, trennen Sie die Werte durch ein Semikolon, z. B. 212;414. Die maximale Länge der Zeichenfolge beträgt 100 Zeichen. Bei jedem Zeichen muss es sich um eine Ziffer von 0 bis 9 handeln.
      

        > [!IMPORTANT]  
        > Stellen Sie sicher, dass der angegebene Wert der Wählmaske nicht mit einer Nummer in einem Orbitbereich zum Parken von Anrufen identisch ist. Das Routing zum Parken von Anrufen hat Vorrang vor der Konvertierung von Notrufwählzeichenfolgen. Um die vorhandenen Orbitbereiche für das Parken von Anrufen zu sehen, klicken Sie in der linken Navigationsleiste auf **"Sprachfunktionen",** und klicken Sie dann auf **"Anruf parken".** 

    
      - **Benachrichtigungs-URI**   Mindestens ein SIP-URIs (Uniform Resource Identifier), der bei einem Notruf benachrichtigt werden soll. Beispielsweise kann die Sicherheitsstelle des Unternehmens durch eine Chatnachricht über jeden Notruf informiert werden. Wenn der Anruferstandort verfügbar ist, wird dieser Standort in die Benachrichtigung aufgenommen. Mehrere SIP-URIs können als eine durch Trennzeichen getrennte Liste angegeben werden. Beispiel: "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". Verteilerlisten werden unterstützt. Die Zeichenfolge muss zwischen 1 und 256 Zeichen lang sein und mit dem Präfix "sip:" beginnen. Bevor Sie in das Feld "Benachrichtigungs-URI" klicken, wird ein Beispiel angezeigt.
    
      - **Konferenz-URI**   Der SIP-URI, in diesem Fall die Telefonnummer, eines Drittanbieters, der bei allen notrufierten Anrufen angerufen wird. Beispielsweise könnte die Sicherheitsstelle des Unternehmens einen Anruf empfangen, wenn ein Notruf abgehört wird, und diesen Anruf abhören oder daran teilnehmen (je nach dem im Feld "Konferenzmodus" angegebenen **Wert).** Die Zeichenfolge muss zwischen 1 und 256 Zeichen lang sein und mit dem Präfix "sip:" beginnen. Es wird ein Beispiel angezeigt, bis Sie in dieses Feld klicken.
    
      - **Konferenzmodus**   Wenn Sie einen Wert im Feld **"Konferenz-URI"** angeben, bestimmt der Konferenzmodus, ob ein Dritter an dem Anruf teilnehmen oder nur zuhören kann.  Geben Sie eine der folgenden Optionen an:
        
          - **One-way**   Ein Drittanbieter kann nur die Unterhaltung zwischen dem Anrufer und der Anbieterin für die Telefonfestnetzanrufe abhören.
        
          - **Zwei-Wege-Methode**   Ein Dritter kann an dem Anruf zwischen dem Anrufer und der Anbieterin für die Telefonfestnetzanrufe teilnehmen und an diesem teilnehmen.

6.  Klicken Sie auf **Commit ausführen**.


    > [!IMPORTANT]  
    > Wenn Sie eine Benutzerrichtlinie erstellen, gilt diese Richtlinie zunächst nicht für Benutzer oder Netzwerkstandorte. Klicken Sie in der linken Navigationsleiste auf **"Benutzer",** um die Richtlinie auf einen Benutzer anzuwenden. Suchen Sie den Benutzer, auf den Sie die Richtlinie anwenden möchten. Klicken Sie im Menü **Bearbeiten** auf **Details einblenden**. Wählen Sie **auf der Seite "Serverbenutzer**  bearbeiten" in der Dropdownliste "Standortrichtlinie" die neue Standortrichtlinie aus, und klicken Sie dann auf **Commit.**<BR>Um die Richtlinie auf einen Netzwerkstandort anzuwenden, klicken Sie **in** der linken Navigationsleiste auf "Netzwerkkonfiguration" und dann auf **"Standort".** Suchen Sie den Netzwerkstandort, auf den Sie die Richtlinie anwenden möchten. Klicken Sie im Menü **Bearbeiten** auf **Details einblenden**. Wählen **Sie in der Dropdownliste**  "Standortrichtlinie" die neue Standortrichtlinie aus, und klicken Sie dann auf **Commit.**


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a>So ändern Sie eine Standortrichtlinie in der Skype for Business Server-Systemsteuerung

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Standortrichtlinie".**

4.  Klicken Sie auf der Seite **Ortungsrichtlinie** auf die Ortungsrichtlinie, die geändert werden soll.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Ändern Sie **auf** der Seite "Standortrichtlinie bearbeiten" die Felder nach Bedarf (Weitere Informationen finden Sie unter Schritt 5 unter "So erstellen Sie eine neue Standortrichtlinie" weiter oben in diesem Thema).

7.  Klicken Sie auf **Commit ausführen**.

        
## <a name="delete-a-location-policy"></a>Löschen einer Standortrichtlinie


1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Standortrichtlinie".**

4.  Klicken Sie auf der Seite **Ortungsrichtlinie** auf die Ortungsrichtlinie, die gelöscht werden soll.
   
    > [!NOTE]  
    > Sie können mehrere Ortungsrichtlinien in einem Arbeitsschritt löschen. Drücken Sie hierzu die STRG-TASTE, und wählen Sie bei gedrückter STRG-TASTE mehrere Richtlinien aus. Wenn Sie alle Richtlinien auswählen möchten, klicken Sie im Menü **Bearbeiten** auf **Alle auswählen**.


5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.

    > [!IMPORTANT]  
    > Die globale Ortungsrichtlinie kann nicht gelöscht werden. Beim Versuch, die globale Richtlinie zu löschen, wird eine Warnmeldung angezeigt, und die Richtlinie wird auf die Standardwerte zurückgesetzt.


## <a name="see-also"></a>Siehe auch

[Erstellen oder Ändern von Netzwerkstandorten](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  

[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 
 
[Remove-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  

[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
