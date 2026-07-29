====================================================================
 SD / ext CONTENT  —  Flipper M5Stick S3 (PUBLIC)
====================================================================

These are the database/asset files that live under /ext on the device:

  subghz/assets/keeloq_mfcodes_user   plaintext (Encryption:0) community
                                      KeeLoq codes — rolling-code decode
  subghz/assets/dangerous_settings    frequency-range unlock toggle
  nfc/assets/*.nfc                    MIFARE / NFC dictionaries + lookups
  infrared/assets/*.ir               universal-remote databases (TV, AC,
                                      audio, fans, LEDs, projectors)

--------------------------------------------------------------------
 You normally do NOT need to copy these by hand.
--------------------------------------------------------------------
The web flasher already writes ALL of these into the device's internal
/ext partition when you flash — this board has no microSD slot, so /ext
lives in flash. This folder is provided for reference, and for adding
the files manually (e.g. via the firmware's Web UI) or onto another
board that does have an SD card: drop the folder contents at the root
of /ext (so you get /ext/subghz, /ext/nfc, /ext/infrared).

--------------------------------------------------------------------
 What is deliberately NOT here (private / proprietary)
--------------------------------------------------------------------
The encrypted (Encryption:1) manufacturer keystores are NOT included in
this public distribution:
  subghz/assets/keeloq_mfcodes    (encrypted manufacturer KeeLoq keys)
  subghz/assets/alutech_at_4n     (encrypted RAW)
  subghz/assets/nice_flor_s       (encrypted RAW)
Without them, plaintext/community rolling codes still decode; encrypted
proprietary manufacturer codes do not. If you own these files, add them
to /ext/subghz/assets/ on your own device.
====================================================================
