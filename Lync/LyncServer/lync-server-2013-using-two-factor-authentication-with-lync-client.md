---
title: Verwenden von zweistufiger Authentifizierung mit dem Lync-Client
TOCTitle: Verwenden von zweistufiger Authentifizierung mit dem Lync-Client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn338071(v=OCS.15)
ms:contentKeyID: 56269347
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwenden von zweistufiger Authentifizierung mit dem Lync-Client

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In diesem Thema wird die Verwendung von zweistufiger Authentifizierung mit dem Lync 2013-Client beschrieben.

## Erstmaliges Anmelden bei Lync 2013

Normalerweise werden Ihre Lync-Anmeldeinformationen bei der Installation von Lync 2013 automatisch konfiguriert. Bei der ersten Verwendung von Lync müssen Sie den Client jedoch möglicherweise manuell starten.

**So melden Sie sich erstmalig bei Lync an**

1.  Melden Sie sich beim Netzwerk Ihrer Organisation an.

2.  Klicken Sie auf **Start** \>**Alle Programme** \> **Microsoft Lync \> Lync 2013**.
    
    Jetzt sollte der Lync-Anmeldebildschirm angezeigt werden.
    
      - Wenn das Feld mit der Anmeldeadresse bereits ausgefüllt ist, überprüfen Sie, ob die angezeigte Adresse richtig ist.
    
      - Wenn sie nicht richtig ist oder das Feld leer ist, geben Sie Ihre Lync-Anmeldeadresse ein (normalerweise ist dies Ihre E-Mail-Adresse).
    
      - Wenn ein leeres Kennwortfeld angezeigt wird, geben Sie Ihr Kennwort ein.

3.  Wählen Sie **Anmelden** aus.

## Abmelden bei Lync

Wenn Sie mit dem Arbeiten in Lync fertig sind, können Sie die Anzeige schließen, sich bei Ihrer Sitzung abmelden oder das Programm schließen – all dies über das Menü "Datei". In der folgenden Tabelle werden die Unterschiede zwischen diesen Optionen erläutert.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Option</th>
<th>Zweck</th>
<th>Vorgehensweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Schließen</p></td>
<td><p>Hiermit wird die Lync-Anzeige geschlossen, die Lync-Sitzung unter Ihrer Benutzer-ID wird jedoch weiterhin ausgeführt. Dies hat den Sinn, dass Sie weiterhin Benachrichtigungen erhalten und sich mit anderen austauschen können.</p>
<p>Sie können die Anzeige jederzeit wiederherstellen, indem Sie in der Taskleiste auf das Lync-Symbol oder unten am Bildschirm auf den Benachrichtigungsbereich klicken.</p></td>
<td><p>Führen Sie im Lync-Hauptfenster eine der folgenden Aktionen aus:</p>
<ol>
<li><p>Wählen Sie die Schaltfläche <strong>Optionen</strong> aus, und wählen Sie dann <strong>Datei</strong> &gt; <strong>Schließen</strong> aus.</p></li>
<li><p>Klicken Sie auf die Schaltfläche <strong>Schließen</strong> (X) in der oberen rechten Ecke des Fensters.</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p>Abmelden</p></td>
<td><p>Hiermit wird die mit Ihrer Benutzer-ID verknüpfte Lync-Sitzung beendet, Lync wird jedoch im Hintergrund weiter ausgeführt. Wenn Sie sich abmelden, wird das Abmeldefenster angezeigt.</p>
<div>

> [!TIP]
> Wählen Sie bei der Abmeldung auf <STRONG>Meine Anmeldeinformationen löschen</STRONG> aus, um den Datensatz mit Ihrer Anmelde-ID und dem Kennwort vom Computer zu entfernen. Dies vereinfacht möglicherweise den Support bei der Behandlung von Anmeldeproblemen. Außerdem trägt es dazu bei, Ihre Anmeldeinformationen zu sichern, da es nicht autorisierten Benutzern so erschwert wird, sich mit Ihren Anmeldeinformationen anzumelden.


</div></td>
<td><p>Wählen Sie im Hauptfenster von Lync die Schaltfläche <strong>Optionen</strong> aus, und wählen Sie dann <strong>Datei</strong> &gt; <strong>Abmelden</strong> aus.</p></td>
</tr>
<tr class="odd">
<td><p>Beenden</p></td>
<td><p>Beendet Ihre Lync-Sitzung und schließt Lync auf dem Computer. Wenn Sie nach dem Beenden Lync erneut starten möchten, wählen Sie <strong>Start</strong> &gt; <strong>Alle Programme</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong> aus.</p></td>
<td><p>Wählen Sie im Hauptfenster von Lync die Schaltfläche <strong>Optionen</strong> aus, und wählen Sie dann <strong>Datei</strong> &gt; <strong>Beenden</strong> aus.</p></td>
</tr>
</tbody>
</table>


## Anmelden bei Lync mit einer SmartCard

Einige Organisationen verwenden mittlerweile einen mehrstufigen Anmeldevorgang, der als zweistufige Authentifizierung bezeichnet wird, um die Sicherheit für ihre Lync 2013-Benutzer zu erhöhen. Wenn von Ihnen die Nutzung dieser Option verlangt wird, benötigen Sie eine "SmartCart", um sich bei Lync anzumelden. SmartCards sind in zwei Formen erhältlich, als physische und als virtuelle Karte:

  - **Physisch**   Ungefähr die Größe einer Kreditkarte. Sie setzen sie für die Anmeldung in ein SmartCard-Lesegerät ein.

  - **Virtuell**   Kein physisches Objekt, sondern eine elektronische ID, die auf einen besonderen Chip auf Ihrem Computer geschrieben wird und auf diese Weise die SmartCard gewissermaßen in den Computer einbaut. Diese Option ist nur für Windows 8-Computer mit TPM-Chip (Trusted Platform Module) verfügbar.

## Registrieren Ihrer SmartCard

Bevor Sie sich mit einer SmartCard anmelden können, muss die Karte "registriert" werden – das bedeutet, dass Ihre Benutzeranmeldeinformationen für die Karte kenntlich gemacht werden müssen. Dies muss unabhängig davon erfolgen, ob es sich um eine physische oder um eine virtuelle Karte handelt. Möglicherweise wurde dieser Vorgang bereits von Ihrem Lync Server-Administrator durchgeführt. Erkundigen Sie sich bei ihm, wenn Sie nicht sicher sind, ob dieser Vorgang bereits ausgeführt wurde.


> [!NOTE]
> Da jede virtuelle SmartCard immer nur dem Gerät zugeordnet ist, auf dem sie installiert ist, wird für jeden Windows&nbsp;8-Computer, den Sie verwenden, eine eigene Karte benötigt.



**So registrieren Sie Ihre SmartCard**

1.  Melden Sie sich bei dem Computer an, auf dem Sie Lync verwenden möchten.

2.  Navigieren Sie im Internet Explorer zur Registrierungsseite der Zertifizierungsstelle Ihrer Organisation.
    
    Fragen Sie Ihren Lync Server-Administrator nach der Webadresse dieser Ressource, wenn Sie sie nicht kennen. Die URL sieht ungefähr wo aus: "https://MyCA.\[ihrfirmenname\].com/certsrv".
    

    > [!NOTE]
    > Wenn Sie Internet Explorer 10 verwenden, müssen Sie diese Website möglicherweise im Kompatibilitätsmodus anzeigen.



3.  Wenn Sie aufgefordert werden, sich auf der Zertifizierungsseite anzumelden, melden Sie sich mit Ihrem Domänenkonto (statt als Administrator Ihres Computers) an.

4.  Wählen Sie auf der Begrüßungsseite die Option **Zertifikat anfordern** aus.

5.  Wählen Sie **Erweiterte Anforderung** aus.

6.  Wählen Sie **Eine Anforderung an diese Zertifizierungsstelle erstellen und einreichen**, und klicken Sie dann auf **Weiter**.

7.  Jetzt wird eine Seite mit dem Titel SmartCard-Registrierungsstelle angezeigt. Genehmigen Sie die Anfrage, das ActiveX-Steuerelement zu installieren, und füllen Sie dann das Formular für die erweiterte Zertifikatanforderung wie folgt aus:
    
    1.  Wählen Sie in der Dropdownliste **Zertifikatvorlage** den Eintrag **SmartCard-Benutzer** aus.
    
    2.  Wählen Sie **Neuen Schlüsselsatz erstellen** aus.
    
    3.  Suchen Sie die Herstellerinformationen auf dem Etikett Ihrer SmartCard, und wählen Sie dann den betreffenden Hersteller in der **CSP**-Dropdownliste aus.
    
    4.  Wählen Sie **CSP** als Anforderungsformat aus, wenn dies noch nicht ausgewählt ist.
    
    5.  Wählen Sie in der Hashalgorithmus-Dropdownliste den Eintrag **sha1** aus, wenn er noch nicht ausgewählt ist.
    
    6.  Geben Sie Ihrem Zertifikat einen Namen, den Sie sich merken können, und klicken Sie dann auf **Senden**.

8.  Legen Sie jetzt Ihre leere SmartCard in das an die Registrierungsstelle angeschlossene SmartCard-Lesegerät, und klicken Sie auf **Registrieren**.

9.  Wenn Sie dazu aufgefordert werden, geben Sie Ihre PIN (Personal Identification Number) ein, und klicken Sie dann auf **OK**.
    

    > [!NOTE]
    > Wenn der für Sie zuständige Mitarbeiter des technischen Supports Ihnen keine besondere PIN für die Registrierung Ihrer SmartCard gegeben hat, verwenden Sie die Standard-PIN für SmartCards, nämlich 12345678.



10. Aktivieren Sie die Option, die den Benutzer (Sie) zwingt, die PIN bei der ersten Verwendung der SmartCard zu ändern.

11. Legen Sie jetzt Ihre leere SmartCard in das an die Registrierungsstelle angeschlossene SmartCard-Lesegerät, und klicken Sie auf **Registrieren**.

12. Wenn Sie dazu aufgefordert werden, geben Sie Ihre PIN (Personal Identification Number) ein, und klicken Sie dann auf **OK**.
    

    > [!NOTE]
    > Wenn der für Sie zuständige Mitarbeiter des technischen Supports Ihnen keine besondere PIN für die Registrierung Ihrer SmartCard gegeben hat, verwenden Sie die Standard-PIN für SmartCards, nämlich 12345678.



13. Aktivieren Sie die Option, die den Benutzer (Sie) zwingt, die PIN bei der ersten Verwendung der SmartCard zu ändern.

14. Klicken Sie auf **OK**, um zu bestätigen, dass das angezeigte Zertifikat Ihre Informationen enthält.

15. Sobald der Hinweis angezeigt wird, dass das Zertifikat ausgestellt wurde, klicken Sie auf **Dieses Zertifikat installieren**, um den Registrierungsvorgang abzuschließen.

## Anmelden bei Lync mit Ihren SmartCard-Anmeldeinformationen

Vor der erstmaligen Verwendung Ihrer SmartCard empfiehlt es sich, auf der Lync-Anmeldeseite auf **Meine Anmeldeinformationen löschen** zu klicken. Dadurch werden alle eventuell auf dem Computer gespeicherten Anmeldeinformationen gelöscht und eine mögliche Fehlerquelle ausgeschaltet.

**So melden Sie sich bei Lync mit Ihren SmartCard-Anmeldeinformationen an**

1.  Starten Sie den Lync-Client.

2.  Geben Sie auf dem Anmeldebildschirm Ihren Benutzerkontonamen für die Anmeldung im Feld **Anmeldeadresse** ein, und klicken Sie dann auf **Anmelden**.

3.  Wenn Sie eine virtuelle SmartCard verwenden, überspringen Sie diesen Schritt.
    
    Wenn Sie eine physische SmartCard verwenden, legen Sie die SmartCard in Ihr SmartCard-Lesegerät ein, wenn Sie dazu aufgefordert werden, und klicken Sie dann auf **OK**, wenn die Karte erkannt wird.

4.  Geben Sie die PIN-Nummer für Ihre SmartCard ein, und klicken Sie dann auf **OK**.
    

    > [!NOTE]
    > Wenn Ihnen keine SmartCard-PIN von Ihrem Supportmitarbeiter zugewiesen wurde, verwenden Sie den Standardwert, nämlich 12345678.


