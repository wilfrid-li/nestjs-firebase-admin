<a href="https://www.npmjs.com/@aginix/nestjs-firebase-admin"><img src="https://img.shields.io/npm/v/@aginix/nestjs-firebase-admin.svg" alt="NPM Version" /></a>
<a href="https://www.npmjs.com/@aginix/nestjs-firebase-admin"><img src="https://img.shields.io/npm/l/@aginix/nestjs-firebase-admin.svg" alt="Package License" /></a>
<a href="https://www.npmjs.com/@aginix/nestjs-firebase-admin"><img src="https://img.shields.io/npm/dm/@aginix/nestjs-firebase-admin.svg" alt="NPM Downloads" /></a>

## Description

Firebase Admin Module for [Nest.js Framework](https://nestjs.com/)
This is a fork of @aginix/nestjs-firebase-admin to support NestJS8 dependencies

## Installation

```bash
$ yarn add @wilfrid-li/nestjs-firebase-admin
```

### Import module

```typescript
import { Module } from '@nestjs/common';
import { FirebaseAdminModule } from '@wilfrid-li/nestjs-firebase-admin'
import * as admin from 'firebase-admin'

@Module({
  imports: [
    FirebaseAdminModule.forRootAsync({
      useFactory: () => ({
        credential: admin.credential.applicationDefault()
      })
    }),
  ],
})
export class AppModule {}
```

## Example

### Inject Authentication Service

```typescript
import { Injectable } from '@nestjs/common';
import { FirebaseAuthenticationService } from '@aginix/nestjs-firebase-admin';

@Injectable()
export class AppService {
  constructor(private firebaseAuth: FirebaseAuthenticationService) {}

  getUsers() {
    return this.firebaseAuth.listUsers()
  }
}
```

## Compatibility Table

| firebase-admin    | NestJS Library |
| ----------------- |----------------|
| `9.xx`            | `master`       |
| `8.xx`            | `1.xx`         |

## License

MIT © [Aginix Technologies Co., Ltd.](https://github.com/Aginix/nestjs-firebase-admin)
