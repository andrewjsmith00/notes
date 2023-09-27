Managed secrets vault. You can store secrets like database credentials and such here. [[Lambda]] is used for rotating credentials.

Secrets are encrypted with [[KMS]]. When a secret is retrieved, you need to decrypt the data as well. Keys are commonly rotated.