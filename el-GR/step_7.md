## Εμφάνιση του ιστορικού άσκησης

Προς το παρόν, η εφαρμογή σου εμφανίζει μόνο τα συνολικά λεπτά άσκησης, αλλά επειδή έχεις τον κατάλογο όλων των μεμονωμένων περιόδων σύνδεσης, γιατί να μην το δείξεις και αυτό;

+ Πήγαινε στην προβολή Designer και πρόσθεσε ένα **ListView** από το **User Interface**.

+ Εάν θέλεις, μπορείς επίσης να προσθέσεις μια ετικέτα πάνω από τη λίστα που να λέει κάτι σαν `Ιστορικό άσκησης:`.

Όπως ίσως έχεις μαντέψει, ένα ListView εμφανίζει μια λίστα με πράγματα. Similar to how you set the Text property of a Label to some text, you set the **Elements** property of a ListView to a list. Θα το κάνεις αυτό σε δύο μέρη στον κώδικά σου.

Πρώτον, πρέπει να ενημερώνεις το ListView κάθε φορά που ο χρήστης εισάγει νέο χρόνο άσκησης.

+ Στο μπλοκ `Button.Click` για το κουμπί `Εισαγωγή`, πρόσθεσε ένα `set ListView.Elements to` μπλοκ και ένα `get global minutesList` μπλοκ κάτω από το `AppendToFile`.

![](images/s8UpdateListViewEls.png)

Δεύτερον, πρέπει να ενημερώσεις το ListView όποτε φορτώνεις το αρχείο λίστας.

+ Find your `File1.GotFile` code, and add `set ListView.Elements to` and `get global minutesList` (the same code as above) right below the `set global minutesList to` block.

![](images/s8SetListViewEls.png)

Και η εφαρμογή σου ολοκληρώθηκε!

--- challenge ---

## Πρόκληση: Παρακολούθησε τον τύπο άσκησης

+ How about adding another TextBox that lets the user also record what kind of exercise they did? Θα πρέπει να σκεφτείς τι επιπλέον κώδικα θα χρειαστείς, όπως λίστες και βρόχους, και πώς θα αποθηκεύσεις τις νέες πληροφορίες σε ένα αρχείο.

+ Μπορείς είτε να χρησιμοποιήσεις το ίδιο αρχείο (με μερικές επιπλέον `join` και `split` εντολές), ή ένα ξεχωριστό.

--- /challenge ---

Μπορείς να δεις ένα παράδειγμα αυτής της εφαρμογής στο App Inventor στο [dojo.soy/intermedapp](http://dojo.soy/intermedapp){: target = "_ blank"}.
