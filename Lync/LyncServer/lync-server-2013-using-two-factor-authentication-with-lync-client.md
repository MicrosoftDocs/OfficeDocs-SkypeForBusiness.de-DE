---
title: 'Lync Server 2013: Verwenden der zweistufigen Authentifizierung mit lync-Client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebe1e31cd0f8c5ff90ba6fa88530236c83e371bf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42116718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a>Verwenden der zweistufigen Authentifizierung mit lync-Client und lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-07-11_

In diesem Thema wird beschrieben, wie Sie die zweistufige Authentifizierung mit lync 2013-Client nutzen.

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a>Erstmalige Anmeldung bei lync 2013

Die lync-Anmeldeinformationen werden normalerweise bei der Installation von lync 2013 automatisch konfiguriert. Das erste Mal, wenn Sie lync verwenden, müssen Sie den Client möglicherweise manuell starten.

**So melden Sie sich zum ersten Mal bei lync an**

1.  Melden Sie sich beim Netzwerk Ihrer Organisation an.

2.  Wählen Sie **Alle Programme** \> **starten** \> **Microsoft \> lync lync 2013**aus.
    
    Der lync-Anmeldebildschirm sollte angezeigt werden.
    
      - Wenn das Feld Anmeldeadresse bereits ausgefüllt ist, vergewissern Sie sich, dass die angezeigte Adresse richtig ist.
    
      - Wenn es nicht richtig ist oder wenn das Feld leer ist, geben Sie Ihre lync-Anmeldeadresse ein (Dies ist normalerweise identisch mit Ihrer e-Mail-Adresse).
    
      - Wenn das Feld leeres Kennwort angezeigt wird, fügen Sie Ihr Kennwort ein.

3.  Wählen Sie **Anmelden**aus.

</div>

<div>

## <a name="sign-out-of-lync"></a>Abmelden bei lync

Wenn Sie lync abgeschlossen haben, können Sie die Anzeige schließen, sich von Ihrer Sitzung abmelden oder aus dem Programm heraus beenden, und zwar im Menü Datei. In der folgenden Tabelle werden die Unterschiede in den Optionen erläutert.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Option</th>
<th>Funktion</th>
<th>Vorgehensweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Schließen</p></td>
<td><p>Schließt die lync-Anzeige, lässt jedoch zu, dass die mit Ihrer Benutzer-ID identifizierte lync-Sitzung weiterhin ausgeführt wird. Dies ist so, dass Sie weiterhin Benachrichtigungen erhalten und mit anderen Personen interagieren können.</p>
<p>Sie können die Anzeige jederzeit wiederherstellen, indem Sie auf der Taskleiste oder im Infobereich am unteren Rand des Bildschirms auf das lync-Symbol klicken.</p></td>
<td><p>Führen Sie im lync-Hauptfenster einen der folgenden Schritte aus:</p>
<ol>
<li><p>Klicken Sie auf die Schaltfläche <strong>Optionen</strong> und anschließend auf <strong>Datei</strong> &gt; <strong>Schließen</strong>.</p></li>
<li><p>Klicken Sie in der oberen rechten Ecke des Fensters auf die Schaltfläche <strong>Schließen</strong> (X).</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p>Abmelden</p></td>
<td><p>Beendet die lync-Sitzung, die Ihrer Benutzer-ID zugeordnet ist, lync wird jedoch weiterhin im Hintergrund ausgeführt. Wenn Sie sich abmelden, wird das Anmeldefenster angezeigt.</p>
<div>

> [!TIP]  
> Wählen Sie beim abmelden die Option <STRONG>Meine Anmeldeinformationen löschen</STRONG> aus, um den Datensatz Ihrer Anmelde-ID und Ihres Kennworts vom Computer zu entfernen. Dadurch wird möglicherweise die Unterstützung von Personen bei der Behandlung von Anmeldeproblemen erleichtert. Es kann auch dazu beitragen, dass Ihre Anmeldeinformationen sicherer sind, da unbefugte Benutzer sich nicht mit Ihren Anmeldeinformationen anmelden können.


</div></td>
<td><p>Wählen Sie im lync-Hauptfenster die Schaltfläche <strong>Optionen</strong> aus, und wählen Sie dann <strong>Datei</strong> &gt; <strong>Abmelden aus</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>Beenden</p></td>
<td><p>Beendet die lync-Sitzung und beendet lync auf Ihrem Computer. Wenn Sie lync nach dem Beenden neu starten möchten, wählen Sie <strong></strong> &gt; <strong>Alle Programme</strong> &gt; starten <strong>Microsoft lync</strong> &gt; <strong>lync 2013</strong>aus.</p></td>
<td><p>Wählen Sie im lync-Hauptfenster die Schaltfläche <strong>Optionen</strong> aus, und wählen Sie dann <strong>Datei</strong> &gt; <strong>Beenden</strong>aus.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a>Anmelden bei lync mit einer Smartcard

Einige Organisationen verwenden jetzt einen mehrstufigen Anmeldevorgang, die sogenannte zweistufige Authentifizierung, um die Sicherheit für Ihre lync 2013 Benutzer zu verbessern. Wenn Sie diese Option voraussichtlich verwenden, benötigen Sie eine Smartcard zur Anmeldung bei lync. Smartcards gibt es in zwei Varianten: physisch und virtuell:

  - **Physische**   Größe einer Kreditkarte. Sie fügen es bei der Anmeldung in ein Smartcard-Lesegerät ein.

  - **Virtual**   kein physisches Objekt, sondern eine elektronische ID, die auf einen speziellen Chip auf Ihrem Computer geschrieben wird, der im Wesentlichen die Smartcard in Ihren Computer einbaut. Nur für die Verwendung mit Windows 8 Computern verfügbar, die den TPM-Chip (Trusted Platform Module) enthalten.

<div>

## <a name="enroll-your-smart-card"></a>Registrieren der Smartcard

Bevor Sie sich mit einer Smartcard anmelden können, muss die Karte "registriert" sein, d. h., Ihre Benutzeranmeldeinformationen müssen mit der Karte identifiziert werden. Dies ist der Fall, wenn die Karte physisch oder virtuell ist. Dieser Vorgang wurde möglicherweise bereits von Ihrem lync Server Administrator ausgeführt. Wenden Sie sich an Sie, wenn Sie nicht sicher sind, ob dies geschehen ist.

<div>


> [!NOTE]  
> Da jede virtuelle Smartcard nur dem Gerät zugeordnet ist, auf dem Sie installiert ist, muss für jeden Windows 8 von Ihnen verwendeten Computer eine separate Karte registriert werden.



</div>

**So registrieren Sie Ihre Smartcard manuell**

1.  Melden Sie sich an dem Computer an, auf dem Sie lync betreiben.

2.  Wechseln Sie mithilfe von Internet Explorer zur Webregistrierungs Seite der Zertifizierungsstelle Ihrer Organisation.
    
    Fragen Sie Ihren lync Server-Administrator nach der Webadresse dieser Ressource, wenn Sie Sie nicht bereits haben. Die URL sieht in etwa wie folgt aus https://MyCA.\: [\]YourCompanyName. com/certsrv.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie Internet Explorer 10 verwenden, müssen Sie diese Website möglicherweise im Kompatibilitätsmodus anzeigen.

    
    </div>

3.  Wenn Sie aufgefordert werden, sich bei der Zertifizierungsseite anzumelden, melden Sie sich mit Ihrem Domänenkonto an (statt als Administrator Ihres Computers).

4.  Wählen Sie auf der Willkommensseite der Website die Option **Zertifikat anfordern**aus.

5.  Wählen Sie **Erweiterte Anforderung**aus.

6.  Wählen Sie **erstellen, und senden Sie eine Anforderung an diese Zertifizierungsstelle, und**klicken Sie dann auf **weiter**.

7.  Jetzt sehen Sie eine Seite namens Smartcard-Registrierungsstelle. Genehmigen Sie die Anforderung zum Installieren des ActiveX-Steuerelements, und füllen Sie dann das Formular für die erweiterte Zertifikatanforderung wie folgt aus:
    
    1.  Wählen Sie in der Dropdownliste **Zertifikatvorlage** die Option **Smartcard-Benutzer** aus.
    
    2.  Wählen Sie **neuen Schlüssel festlegen erstellen**aus.
    
    3.  Suchen Sie die Herstellerinformationen auf dem Etikett Ihrer Smartcard, und wählen Sie diesen Hersteller in der Dropdownliste **CSP** aus.
    
    4.  Wählen Sie **CSP** als Anforderungs Format aus, sofern es nicht bereits ausgewählt ist.
    
    5.  Wählen Sie in der Dropdownliste Hash Algorithmus die Option **SHA1** aus, sofern Sie noch nicht ausgewählt ist.
    
    6.  Geben Sie Ihrem Zertifikat einen Namen, den Sie erkennen, und klicken Sie auf über **Mitteln**.

8.  Legen Sie jetzt Ihre leere Smartcard in das Kartenlesegerät ein, das mit der Registrierungsstelle verbunden ist, und klicken Sie auf **registrieren**.

9.  Wenn Sie dazu aufgefordert werden, geben Sie Ihre persönliche Identifikationsnummer (PIN) ein, und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Ihr technischer Support-Mitarbeiter Ihnen keine spezielle PIN für die Registrierung Ihrer Smartcard gegeben hat, verwenden Sie den standardmäßigen Smartcard-PIN-Wert, also 12345678.

    
    </div>

10. Wählen Sie die Option aus, um zu erzwingen, dass der Benutzer die PIN ändert, wenn die Smartcard zum ersten Mal verwendet wird.

11. Legen Sie jetzt Ihre leere Smartcard in das Kartenlesegerät ein, das mit der Registrierungsstelle verbunden ist, und klicken Sie auf **registrieren**.

12. Wenn Sie dazu aufgefordert werden, geben Sie Ihre persönliche Identifikationsnummer (PIN) ein, und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Ihr technischer Support-Mitarbeiter Ihnen keine spezielle PIN für die Registrierung Ihrer Smartcard gegeben hat, verwenden Sie den standardmäßigen Smartcard-PIN-Wert, also 12345678.

    
    </div>

13. Wählen Sie die Option aus, um zu erzwingen, dass der Benutzer die PIN ändert, wenn die Smartcard zum ersten Mal verwendet wird.

14. Klicken Sie auf **OK** , um zu bestätigen, dass das angezeigte Zertifikat über Ihre Informationen verfügt.

15. Wenn Sie festgestellt haben, dass das Zertifikat ausgestellt wurde, klicken Sie auf **dieses Zertifikat installieren** , um den Registrierungsvorgang abzuschließen.

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a>Anmelden bei lync mit ihren Smartcard-Anmeldeinformationen

Bevor Sie Ihre Smartcard zum ersten Mal verwenden, sollten Sie auf der lync-Anmeldeseite auf **Meine Anmeldeinformationen löschen** klicken. Dadurch werden alle auf Ihrem Computer gespeicherten Anmeldeinformationen gelöscht, und eine mögliche Fehlerquelle wird eliminiert.

**So melden Sie sich mit ihren Smartcard-Anmeldeinformationen bei lync an**

1.  Starten Sie den lync-Client.

2.  Geben Sie auf dem Anmeldebildschirm den Namen Ihres Anmeldebenutzer Kontos in das Feld **Anmeldeadresse** ein, und klicken Sie dann auf **Anmelden**.

3.  Wenn Sie eine virtuelle Smartcard verwenden, überspringen Sie diesen Schritt.
    
    Wenn Sie eine physische Smartcard verwenden, legen Sie die Smartcard in das Smartcard-Lesegerät ein, und klicken Sie dazu auf OK, und klicken Sie dann auf **OK** , wenn die Karte erkannt wird.

4.  Geben Sie die PIN-Nummer für Ihre Smartcard ein, und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie Ihrer Support Person keine Smartcard-PIN-Nummer zugewiesen haben, verwenden Sie den Standardwert 12345678.

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

