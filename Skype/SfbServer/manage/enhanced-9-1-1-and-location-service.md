---
title: Verwalten der erweiterten 9-1-1 und des Standortdiensts
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Skype for Business Server unterstützt erweiterte 9-1-1 (E9-1-1)-Anrufe von Skype for Business Clients. Wenn Sie Skype for Business Server für E9-1-1 konfigurieren, enthalten Notrufe, die von Skype for Business getätigt werden, Informationen zum Notfalleinsatzstandort (EMERGENCY Response Location, ERL) aus der Standortinformationsdienstdatenbank.
ms.openlocfilehash: 5b002e4043cb400b5f22a4b11bc70941a88abc2a
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676007"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a>Verwalten der erweiterten 9-1-1 und des Standortdiensts in Skype für Busines Server

Skype for Business Server unterstützt erweiterte 9-1-1 (E9-1-1)-Anrufe von Skype for Business Clients. Wenn Sie Skype for Business Server für E9-1-1 konfigurieren, enthalten Notrufe, die von Skype for Business getätigt werden, Informationen zum Notfalleinsatzstandort (EMERGENCY Response Location, ERL) aus der Standortinformationsdienstdatenbank. Verwenden Sie die Verfahren in diesem Artikel, um die Standortrichtlinie zu verwalten.

> [!Note]
> Ausführliche Informationen zur Bereitstellung erweiterter Enterprise-VoIP Features wie E9-1-1 und dem Standortinformationsdienst finden [Sie unter Bereitstellen erweiterter Enterprise-VoIP-Features](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md).

In Skype for Business Server können Sie die Standortrichtlinie verwenden, um Einstellungen anzuwenden, die sich auf die Erweiterte 9-1-1(E9-1-1)-Funktionalität beziehen, und auf Standorteinstellungen für Benutzer oder Kontakte. Die Standortrichtlinie bestimmt, ob ein Benutzer für E9-1-1 aktiviert ist und wenn ja, welches Verhalten ein Notruf hat. Mithilfe der Standortrichtlinie können Sie beispielsweise definieren, welche Nummer einen Notruf darstellt (z. B. 911 im USA), ob die Unternehmenssicherheit automatisch benachrichtigt werden soll und wie der Anruf weitergeleitet werden soll.

Sie können Standortrichtlinien aus der Gruppe **"Netzwerkkonfiguration"** im Skype for Business Server Systemsteuerung konfigurieren. In der Skype for Business Server Systemsteuerung können Sie Standortrichtlinien anzeigen, erstellen, ändern oder löschen. Verwenden Sie das folgende Verfahren, um Informationen zu Ortungsrichtlinien anzuzeigen. 


## <a name="view-location-policy-information"></a>Standortrichtlinieninformationen anzeigen 

1.  Melden Sie sich von einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei jedem Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf " **Standortrichtlinie"**.

4.  Klicken Sie auf der Seite **Ortungsrichtlinie** auf die Ortungsrichtlinie, die geändert werden soll.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.
 
    > [!NOTE]  
    > Sie können jeweils nur Informationen zu einer Ortungsrichtlinie anzeigen.

Standardmäßig ist eine einzige Richtlinie (Global) vorhanden, die nicht gelöscht oder umbenannt werden kann. Sie können die globale Richtlinie jedoch ändern. Sofern keine Standortrichtlinien oder Richtlinien auf Benutzerbasis erstellt werden, wird diese Richtlinie auf sämtliche Benutzer und Kontakte angewendet. Richtlinien auf Benutzerbasis müssen auf bestimmte Benutzer angewendet werden.


## <a name="create-or-modify-a-location-policy"></a>Erstellen oder Ändern einer Standortrichtlinie 

In Skype for Business Server können Sie die Standardzeit zwischen Clientanforderungen für eine Standortaktualisierung vom Standortinformationsdienst außer Kraft setzen. Der Standardwert ist 4 Stunden. Verwenden Sie das **Cmdlet Set-CsLocationPolicy** mit dem Parameter "LocationRefreshInterval", um den Standardwert zu überschreiben.


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a>So erstellen Sie eine neue Standortrichtlinie im Skype for Business Server Systemsteuerung

1.  Melden Sie sich von einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei jedem Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf " **Standortrichtlinie"**.

4.  Klicken Sie auf der Seite " **Standortrichtlinie** " auf **"Neu** ", und wählen Sie dann den Typ der Richtlinie aus, die Sie erstellen möchten:
    
      - Klicken Sie auf "Websiterichtlinie", um eine **Websiterichtlinie** zu erstellen. **Wählen Sie in "Website auswählen**" die Website aus, auf die die Richtlinie angewendet werden soll, und klicken Sie auf **"OK**". Auf der Seite " **Neue Standortrichtlinie** " enthält das Feld **"Bereich** " den Wert **"Website**", und das Feld " **Name** " enthält den Namen der ausgewählten Website. Sie können keines dieser Felder ändern. Eine Websiterichtlinie wird automatisch auf alle Benutzer am angegebenen Standort angewendet und setzt die globale Richtlinie für diese Benutzer außer Kraft.
    
      - Klicken Sie auf **Benutzerrichtlinie**, um eine **Benutzerrichtlinie** zu erstellen. In der **Neuen Standortrichtlinie** enthält das Feld **"Bereich** " den Wert **"Benutzer**". Sie können diesen Wert nicht ändern. Geben Sie im Feld **"Name** " den Namen ein, den Sie dieser Richtlinie zuweisen möchten. Eine Benutzerrichtlinie gilt nicht automatisch für Benutzer. Nachdem Sie die Benutzerrichtlinie erstellt haben, müssen Sie die Richtlinie manuell den Benutzern oder Netzwerkstandorten gewähren, auf die Sie die Richtlinie anwenden möchten.

5.  Füllen Sie die verbleibenden Felder wie folgt aus:
    
      - **Aktivieren erweiterter Notfalldienste**   Aktivieren Sie dieses Kontrollkästchen, um die Benutzer zu aktivieren, die dieser Richtlinie für E9-1-1 zugeordnet sind. Wenn Notrufdienste aktiviert sind, rufen Skype for Business Server Clients Standortinformationen zur Registrierung ab und enthalten diese Informationen, wenn ein Notruf getätigt wird.
    
      - **Lage**   Geben Sie einen der folgenden Werte an:
        
          - **Erforderlich**   Der Benutzer wird aufgefordert, Standortinformationen einzugeben, wenn sich der Client an einem neuen Speicherort registriert. Der Benutzer kann die Eingabeaufforderung ohne Eingabe von Informationen verwerfen. Wenn Informationen eingegeben werden, wird zuerst ein Notruf vom Notdienstanbieter entgegen genommen, um den Standort zu überprüfen, bevor er an den PsAP-Betreiber (Public Safety Answering Point, 911) weitergeleitet wird.
        
          - **Nicht erforderlich**   Der Benutzer wird nicht zur Eingabe eines Standorts aufgefordert. Wenn ein Anruf ohne Standortinformationen erfolgt, nimmt der Notdienstanbieter den Anruf entgegen und fragt nach einem Standort.
        
          - **Haftungsausschluss**   Diese Option ist identisch mit **"Erforderlich"** , mit der Ausnahme, dass der Benutzer die Eingabeaufforderung nicht schließen kann, ohne Standortinformationen einzugeben. Der Benutzer kann weiterhin einen Notruf abschließen, aber ohne Eingabe der Informationen können keine weiteren Anrufe ausgeführt werden. Darüber hinaus wird dem Benutzer Haftungsausschlusstext angezeigt, der sie über die Folgen der Ablehnung der Eingabe von Standortinformationen informieren kann. Zum Festlegen des Haftungsausschlusstexts müssen Sie die Skype for Business Server-Verwaltungsshell verwenden, um das Cmdlet **"Set-CsLocationPolicy**" oder das Cmdlet **"New-CsLocationPolicy**" mit dem Parameter "EnhancedEmergencyServiceDisclaimer" auszuführen. Ausführliche Informationen finden [Sie unter Set-CsLocationPolicy](/powershell/module/skype/Set-CsLocationPolicy) oder [New-CsLocationPolicy](/powershell/module/skype/New-CsLocationPolicy).
          
    
      - **Verwenden Sie den Standort nur für Notfalldienste**, Skype for Business standortinformationen aus verschiedenen Gründen verwenden können (z. B. um Teamkollegen über Ihren aktuellen Standort zu informieren). Aktivieren Sie dieses Kontrollkästchen, um sicherzustellen, dass Standortinformationen nur für die Verwendung mit einem Notruf verfügbar sind.
    
      - **PSTN-Verwendung**   Die PSTN-Nutzung (Public Switched Telephone Network), die verwendet wird, um zu bestimmen, welche VoIP-Route zum Weiterleiten von Notrufen von Clients verwendet wird, die dieses Profil verwenden. Die dieser Verwendung zugeordnete Route muss auf einen SIP-Trunk verweisen, der speziell für Notrufe eingerichtet wurde, oder auf ein ELIN (Emergency Location Identification Number)-Gateway, das den Notruf an die nächstgelegene Rettungsleitstelle weiterleitet.
    
      - **Notrufnummer**   Die Nummer, die gewählt wird, um die Notrufdienste zu erreichen. In den USA lautet dieser Wert "911". Die Zeichenfolge muss aus den Ziffern 0 bis 9 bestehen und kann 1 bis 10 Ziffern umfassen.
    
      - **Notruf-Wählmaske**   Eine Zahl, die Sie in den Wert des Notrufnummernwerts übersetzen möchten, wenn er gewählt wird. Wenn Sie z. B. den Wert 212 in dieses Feld eingeben und das Feld für die Notrufnummer den Wert 911 aufweist, wird der Anruf an 911 getätigt, wenn ein Benutzer 212 wählt. Auf diese Weise können auch andere Notrufnummern eingerichtet werden, mit denen dennoch die Notrufdienste erreicht werden. (Dies ist beispielsweise hilfreich, wenn jemand aus einem Land oder einer Region mit einer anderen Notrufnummer versucht, die Notrufnummer des eigenen Lands zu wählen, und nicht die Notrufnummer des Lands oder der Region, in dem/der er sich gerade aufhält.) Um mehrere Notrufmasken zu definieren, trennen Sie die Werte durch ein Semikolon, z. B. 212;414. Die maximale Länge der Zeichenfolge beträgt 100 Zeichen. Bei jedem Zeichen muss es sich um eine Ziffer von 0 bis 9 handeln.
      

        > [!IMPORTANT]  
        > Stellen Sie sicher, dass der angegebene Wählmaskenwert nicht mit einer Nummer in einem Orbitbereich zum Parken von Anrufen übereinstimmt. Das Routing des Parkens von Anrufen hat Vorrang vor der Konvertierung von Notrufwählzeichenfolgen. Wenn Sie die vorhandenen Orbitbereiche für das Parken von Anrufen anzeigen möchten, klicken Sie auf der linken Navigationsleiste auf " **VoIP-Features** ", und klicken Sie dann auf **"Parken von Anrufen**". 

    
      - **Benachrichtigungs-URI**   Eine oder mehrere SIP Uniform Resource Identifiers (URIs), die benachrichtigt werden sollen, wenn ein Notruf erfolgt. Beispielsweise kann die Sicherheitsstelle des Unternehmens durch eine Chatnachricht über jeden Notruf informiert werden. Wenn der Anruferstandort verfügbar ist, wird dieser Standort in die Benachrichtigung aufgenommen. Mehrere SIP-URIs können als eine durch Trennzeichen getrennte Liste angegeben werden. Beispiel: "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". Verteilerlisten werden unterstützt. Die Zeichenfolge muss zwischen 1 und 256 Zeichen lang sein und mit dem Präfix "sip:" beginnen. Bevor Sie in das Benachrichtigungs-URI-Feld klicken, wird ein Beispiel angezeigt.
    
      - **Konferenz-URI**   Der SIP-URI, in diesem Fall die Telefonnummer eines Drittanbieters, der in notrufe eingerufen wird. Beispielsweise könnte die Sicherheitsstelle des Unternehmens einen Anruf erhalten, wenn ein Notruf getätigt wird, und diesen Anruf abhören oder daran teilnehmen (je nach dem im Feld " **Konferenzmodus** " angegebenen Wert). Die Zeichenfolge muss zwischen 1 und 256 Zeichen lang sein und mit dem Präfix "sip:" beginnen. Ein Beispiel wird angezeigt, bis Sie in dieses Feld klicken.
    
      - **Konferenzmodus**   Wenn Sie im **Feld "Konferenz-URI** " einen Wert angeben, bestimmt der **Konferenzmodus** , ob ein Dritter am Anruf teilnehmen oder nur lauschen kann. Geben Sie eine der folgenden Optionen an:
        
          - **Unidirektionale**   Ein Drittanbieter kann nur die Unterhaltung zwischen dem Anrufer und dem PSAP-Operator anhören.
        
          - **Bidirektionale**   Ein Dritter kann sich den Anruf zwischen dem Anrufer und dem PSAP-Betreiber anhören und daran teilnehmen.

6.  Klicken Sie auf **Commit ausführen**.


    > [!IMPORTANT]  
    > Wenn Sie eine Benutzerrichtlinie erstellen, gilt diese Richtlinie zunächst nicht für Benutzer oder Netzwerkstandorte. Wenn Sie die Richtlinie auf einen Benutzer anwenden möchten, klicken Sie auf der linken Navigationsleiste auf **"Benutzer** ". Suchen Sie den Benutzer, auf den Sie die Richtlinie anwenden möchten. Klicken Sie im Menü **Bearbeiten** auf **Details einblenden**. Wählen Sie auf der Seite " **Serverbenutzer bearbeiten** " die neue Standortrichtlinie aus der Dropdownliste " **Standortrichtlinie"** aus, und klicken Sie dann auf " **Commit ausführen**".<BR>Wenn Sie die Richtlinie auf einen Netzwerkstandort anwenden möchten, klicken Sie auf der linken Navigationsleiste auf **"Netzwerkkonfiguration** " und dann auf **"Website"**. Suchen Sie den Netzwerkstandort, auf den Sie die Richtlinie anwenden möchten. Klicken Sie im Menü **Bearbeiten** auf **Details einblenden**. Wählen **Sie in "Website bearbeiten**" die neue Standortrichtlinie aus der Dropdownliste " **Standortrichtlinie"** aus, und klicken Sie dann auf **"Commit ausführen"**.


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a>So ändern Sie eine Standortrichtlinie im Skype for Business Server Systemsteuerung

1.  Melden Sie sich von einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei jedem Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf " **Standortrichtlinie"**.

4.  Klicken Sie auf der Seite **Ortungsrichtlinie** auf die Ortungsrichtlinie, die geändert werden soll.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Ändern Sie auf der Seite " **Standortrichtlinie bearbeiten** " die Felder nach Bedarf (ausführliche Informationen finden Sie in Schritt 5 in den Verfahren "So erstellen Sie eine neue Standortrichtlinie" weiter oben in diesem Thema).

7.  Klicken Sie auf **Commit ausführen**.

        
## <a name="delete-a-location-policy"></a>Löschen einer Standortrichtlinie


1.  Melden Sie sich von einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei jedem Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf " **Standortrichtlinie"**.

4.  Klicken Sie auf der Seite **Ortungsrichtlinie** auf die Ortungsrichtlinie, die gelöscht werden soll.
   
    > [!NOTE]  
    > Sie können mehrere Ortungsrichtlinien in einem Arbeitsschritt löschen. Drücken Sie hierzu die STRG-TASTE, und wählen Sie bei gedrückter STRG-TASTE mehrere Richtlinien aus. Wenn Sie alle Richtlinien auswählen möchten, klicken Sie im Menü **Bearbeiten** auf **Alle auswählen**.


5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.

    > [!IMPORTANT]  
    > Die globale Ortungsrichtlinie kann nicht gelöscht werden. Beim Versuch, die globale Richtlinie zu löschen, wird eine Warnmeldung angezeigt, und die Richtlinie wird auf die Standardwerte zurückgesetzt.


## <a name="see-also"></a>Siehe auch

[Erstellen oder Ändern von Netzwerkstandorten](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[New-CsLocationPolicy](/powershell/module/skype/New-CsLocationPolicy)  

[Set-CsLocationPolicy](/powershell/module/skype/Set-CsLocationPolicy) 
 
[Remove-CsLocationPolicy](/powershell/module/skype/Remove-CsLocationPolicy)  

[Get-CsLocationPolicy](/powershell/module/skype/Get-CsLocationPolicy)