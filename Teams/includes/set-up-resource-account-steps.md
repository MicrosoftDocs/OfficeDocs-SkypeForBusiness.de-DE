In Microsoft Teams ist für jede automatische Telefonzentrale oder Anrufwarteschleife ein Ressourcenkonto erforderlich. Ressourcenkonten können auch Diensttelefonnummern zugewiesen werden. Auf diese Weise weisen Sie Automatischen Telefonzentralen und Anrufwarteschleifen Telefonnummern zu, sodass Anrufer von außerhalb von Teams die automatische Telefonzentrale oder Anrufwarteschleife erreichen können.

In diesem Artikel wird beschrieben, wie Sie Ressourcenkonten erstellen und für die Verwendung mit automatischen Telefonzentralen und Anrufwarteschleifen vorbereiten.

Bevor Sie mit den Verfahren in diesem Artikel beginnen, stellen Sie sicher, dass Sie Folgendes getan haben:

- [Abrufen Microsoft Teams Telefon Ressourcenkontolizenzen](#obtain-microsoft-teams-phone-resource-account-licenses)
- [Abrufen von Servicenummern](#obtain-service-numbers)

> [!NOTE]
> Ressourcenkonten, die für automatische Telefonzentralen und Anrufwarteschleifen verwendet werden, sind für die Anmeldung deaktiviert und müssen so bleiben. Chat und Anwesenheit sind für diese Konten nicht verfügbar.

### <a name="obtain-microsoft-teams-phone-resource-account-licenses"></a>Abrufen Microsoft Teams Telefon Ressourcenkontolizenzen

Jedes Ressourcenkonto benötigt eine Lizenz, um mit automatischen Telefonzentralen und Anrufwarteschleifen arbeiten zu können. Sie können eine kostenlose *Microsoft Teams Telefon Resource Account-Lizenz* verwenden. Informationen zum Abrufen dieser Lizenzen finden Sie [unter Microsoft Teams Telefon Ressourcenkontolizenzen](../teams-add-on-licensing/virtual-user.md).

Weiter unten in diesem Artikel erfahren Sie, wie Sie [die Lizenz einem Ressourcenkonto zuweisen](#assign-a-license).

Wenn Sie **Teams Telefon Standard**- oder **Teams Phone with Calling Plan-Bundlelizenzen** erworben haben, sind Microsoft *Teams Phone-Ressourcenkontolizenzen* bereits in Ihrem Konto vorhanden.

Um festzustellen, ob Sie bereits über Ressourcenkontolizenzen verfügen, melden Sie sich bei Microsoft 365 mit einem Konto mit globalen Administratorberechtigungen an. Wechseln Sie dann zu [Abrechnung > Ihre Produkte](https://admin.microsoft.com/Adminportal/Home#/subscriptions). Wenn Sie über Ressourcenkontolizenzen verfügen, werden diese als **Microsoft Teams Telefon Ressourcenkonto** angezeigt.

1. Öffnen Sie die Microsoft 365 Admin Center, und melden Sie sich mit einem Benutzer an, der ein globaler Administrator ist. Dies ist normalerweise das Konto, das Sie für die Registrierung für Microsoft 365 verwendet haben.
2. Wechseln Sie im linken Navigationsbereich zu **Den Add-Ons** >  "[**Abrechnungskaufdienste** > ](https://admin.microsoft.com/Adminportal/Home#/catalog) > **" alle Add-Ons-Produkte anzeigen**.
3. Scrollen Sie bis zum Ende, um die **Lizenz für das Microsoft Teams Telefon Ressourcenkonto** zu finden. Wählen Sie **"Details**" und dann **"Kaufen"** aus.
4. Wählen Sie auf der Seite "Lizenzkauf" die anzahl der gewünschten Ressourcenkontolizenzen aus. Sie benötigen eine Ressourcenkontolizenz für jede automatische Telefonzentrale und Anrufwarteschleife, die Sie einrichten möchten. Es wird empfohlen, mindestens fünf Lizenzen auszuwählen, damit Sie in Zukunft problemlos mehr automatische Telefonzentralen und Anrufwarteschleifen einrichten können, ohne sofort weitere Lizenzen erwerben zu müssen.
5. Deaktivieren Sie die Option **"Automatisch allen Benutzern ohne Lizenzen zuweisen**".
6. Wählen Sie **"Jetzt auschecken" aus**.
7. Bestätigen Sie Ihre Bestellung, wählen Sie **"Weiter**" und dann **"Bestellung aufgeben"** aus.

Es entstehen keine Kosten, Sie müssen jedoch dennoch die diese Schritte befolgen, um die Lizenz zu erwerben.

### <a name="obtain-service-numbers"></a>Abrufen von Servicenummern

Servicenummern sind für automatische Telefonzentralen und Anrufwarteschleifen optional. Sie benötigen jedoch mindestens eine Servicenummer, damit Anrufer Ihre automatische Telefonzentrale und Anrufwarteschleifenkonfiguration erreichen können. Für alle automatischen Telefonzentralen oder Anrufwarteschleifen, die sie direkt über eine Dienstnummer erreichen möchten, benötigen Sie ein Ressourcenkonto mit einer zugeordneten Dienstnummer.

Ressourcenkonten können gebührenpflichtige oder gebührenfreie Servicenummern verwenden. Sie können neue Nummern anfordern oder vorhandene Nummern von einem anderen Netzbetreiber portiert.

Informationen zum Abrufen neuer Servicenummern finden [Sie unter "Abrufen von Servicetelefonnummern"](../getting-service-phone-numbers.md).

Informationen zum Portieren einer Nummer von einem anderen Netzbetreiber finden Sie unter [Übertragen von Telefonnummern zu Teams](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

## <a name="create-a-resource-account"></a>Erstellen eines Ressourcenkontos

Sie können ein Ressourcenkonto im Teams Admin Center erstellen.

1. Erweitern Sie im Teams Admin Center **VoIP**, und wählen Sie dann **Ressourcenkonten aus**.
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie im Bereich "**Ressourcenkonto hinzufügen****" den Anzeigenamen**, **den Benutzernamen** und den **Ressourcenkontotyp** ein. Der Ressourcenkontotyp kann entweder eine **automatische Telefonzentrale** oder **eine Anrufwarteschleife** sein, je nachdem, wie Sie dieses Ressourcenkonto verwenden möchten.
4. Klicken Sie auf **Speichern**.

## <a name="assign-a-license"></a>Zuweisen einer Lizenz

Für jedes Ressourcenkonto müssen Sie eine *Microsoft Teams Telefon Ressourcenkontolizenz* oder *Teams Telefon Standard* Lizenz zuweisen.

1. Erweitern Sie im Microsoft 365 Admin Center **"Benutzer"**, und wählen Sie dann **"Aktive Benutzer**" aus.
2. Wählen Sie das Ressourcenkonto aus, dem Sie eine Lizenz zuweisen möchten. Der Benutzerbereich des Ressourcenkontos wird angezeigt.
3. Wählen Sie auf der Registerkarte **"Lizenzen und Apps**" unter **"Lizenzen****" Microsoft Teams Telefon Ressourcenkonto** aus.
4. Wählen Sie **"Änderungen speichern" aus**.

## <a name="assign-a-service-number"></a>Zuweisen einer Dienstnummer

Wenn Sie planen, das Ressourcenkonto mit einer automatischen Telefonzentrale oder Anrufwarteschleife zu verwenden, für die eine Dienstnummer erforderlich ist, weisen Sie dem Ressourcenkonto eine Nummer zu.

1. Wählen Sie im Teams Admin Center auf der Seite " **Ressourcenkonten"** das Ressourcenkonto aus, dem Sie eine Dienstnummer zuweisen möchten, und wählen Sie dann " **Zuweisen/Zuweisung aufheben**" aus.
2. Wählen Sie im Dropdownmenü " **Telefonnummerntyp** " den Typ der Nummer aus, die Sie verwenden möchten.
3. Suchen Sie im Feld **"Zugewiesene Telefonnummer** " nach der Nummer, die Sie verwenden möchten, und wählen Sie **"Hinzufügen"** aus. Achten Sie darauf, die Ländervorwahl anzugeben (z. B. +1 250 555 0012).
4. Klicken Sie auf **Speichern**.

Um einem Ressourcenkonto eine direkte Routing- oder Hybridnummer zuzuweisen, müssen Sie PowerShell verwenden:

`Set-CsPhoneNumberAssignment -Identity aa-contoso_main@contoso64.net -PhoneNumber +19295550150 -PhoneNumberType DirectRouting`