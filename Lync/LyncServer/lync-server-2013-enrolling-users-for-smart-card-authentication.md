---
title: Registrieren von Benutzern für die SmartCard-Authentifizierung
TOCTitle: Registrieren von Benutzern für die SmartCard-Authentifizierung
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn308570(v=OCS.15)
ms:contentKeyID: 56269324
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Registrieren von Benutzern für die SmartCard-Authentifizierung

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Allgemein bestehen zwei Verfahren für das Registrieren von Benutzern für die SmartCart-Authentifizierung. Das einfachere Verfahren sieht die direkte Registrierung der Benutzer für die SmartCard-Authentifizierung mithilfe der Webregistrierung vor, während bei der komplexeren Methode ein Enrollment Agent verwendet wird. Dieses Thema legt den Schwerpunkt auf die Selbstregistrierung der Benutzer für SmartCard-Zertifikate.

Weitere Informationen zur Registrierung im Auftrag von Benutzern als Enrollment Agent finden Sie in "Registrieren von Zertifikaten im Auftrag von anderen Benutzern" unter [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).

## So registrieren Sie Benutzer für die SmartCard-Authentifizierung

1.  Melden Sie sich bei der Windows 8-Arbeitsstation mit den Anmeldeinformationen eines für Lync aktivierten Benutzers an.

2.  Starten Sie Internet Explorer.

3.  Navigieren Sie zur Seite **Zertifizierungsstellen-Webregistrierung** (z. B. "https://MyCA.contoso.com/certsrv").
    

    > [!NOTE]
    > Wenn Sie Internet Explorer 10 verwenden, müssen Sie diese Website möglicherweise im Kompatibilitätsmodus anzeigen.



4.  Wählen Sie auf der Seite **Willkommen** die Option **Zertifikat anfordern** aus.

5.  Wählen Sie im nächsten Schritt **Erweiterte Anforderung** aus.

6.  Wählen Sie **Eine Anforderung an diese Zertifizierungsstelle erstellen und einreichen** aus.

7.  Wählen Sie im Abschnitt **Zertifikatvorlage** den Eintrag **SmartCard-Benutzer** aus, und füllen Sie die erweiterte Zertifikatanforderung mit den folgenden Werten aus:
    
      - **Schlüsseloptionen** – bestätigen Sie die folgenden Einstellungen:
        
          - Aktivieren Sie das Optionsfeld **Neuen Schlüsselsatz erstellen**
        
          - Wählen Sie für **CSP** die Option **Microsoft Basis-SmartCard-Krypto-Anbieter**
        
          - Wählen Sie für **Schlüsselverwendung** den Wert **Exchange** aus (dies ist die einzige verfügbare Option).
        
          - Geben Sie unter **Schlüsselgröße** den Wert **2048** ein
        
          - Überprüfen Sie, ob **Automatischer Schlüsselcontainername** aktiviert ist
        
          - Lassen Sie die anderen Felder deaktiviert.
    
      - Bestätigen Sie unter **Weitere Optionen** die folgenden Werte:
        
          - Wählen Sie für **Anforderungsformat** den Wert **CMC** aus.
        
          - Wählen Sie für **Hashalgorithmus** den Wert **sha1** aus.
        
          - Geben Sie als **Anzeigename** den Wert **Smardcardzertifikat** ein.

8.  Wenn Sie ein physisches Smartcard-Lesegerät verwenden, setzen Sie die SmartCard in das Gerät ein.

9.  Klicken Sie auf **Senden**, um die Zertifikatanforderung einzureichen.

10. Wenn Sie dazu aufgefordert werden, geben Sie die PIN ein, die zum Erstellen der virtuellen SmartCard verwendet wurde.
    

    > [!NOTE]
    > Der Standardwert der PIN für virtuelle SmartCards ist "12345678".



11. Nachdem das Zertifikat ausgestellt wurde, klicken Sie auf **Dieses Zertifikat installieren**, um den Registrierungsvorgang abzuschließen.
    

    > [!NOTE]
    > Wenn bei der Zertifikatanforderung ein Fehler mit der Meldung "Der Webbrowser unterstützt nicht die Generierung von Zertifikatanforderungen" auftritt, kann das Problem auf drei verschiedene Weisen gelöst werden: 
    > <OL>
    > <LI>
    > <P>Aktivieren Sie in Internet Explorer die Kompatibilitätsansicht</P>
    > <LI>
    > <P>Aktivieren Sie die Option "Intraneteinstellungen einschalten" in Internet Explorer</P>
    > <LI>
    > <P>Aktivieren Sie in den Internet Explorer-Optionen auf der Registerkarte "Sicherheit" die Einstellung "Alle Zonen auf Standardstufe zurücksetzen".</P></LI></OL>


