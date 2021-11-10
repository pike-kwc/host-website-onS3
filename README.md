# Host an SPA on s3 with routing

AWS S3で reactのアプリをホストするプロジェクト

***%これはReactの勉強のためではない***

## 必要な物

- AWS account
- [AWS cli](https://docs.aws.amazon.com/ja_jp/cli/latest/userguide/cli-chap-configure.html)
- [PNPM](https://pnpm.io/installation)又は[NPM](https://docs.npmjs.com/cli/v6/commands/npm-install)

## AWS上で使用サービス

- S3 Bucket
- CloudFront

## デプロイ

1. s3 bucket を作って

2. ```bash
    $PNPM build
    ```

3. Cloud Frontのdistributionを作って![CloudFront](/docs/distributionSS.png)
    - Enable OAI bucket access
    - Update the bucket policy

4. Set custom error codes for 404 and 403 ![ErrorCodes](/docs/errorcodes.png)
5. Upload to the s3 bucket `aws s3 sync build/ s3://{your-s3-bucket}`
