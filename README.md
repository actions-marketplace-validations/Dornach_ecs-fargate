# amazon-ECS-deploy

The script uses files: configure-aws-credentials@v1

https://github.com/aws-actions/configure-aws-credentials

## Sample use
```yaml
      - name: Update an AWS ECS service with the new image
        uses: ./ZieglerLabs/amazon-ECS-deploy@v1.1
        with:
          tags: '[{"containerImage":"api","tag":"ziegler-cards-api","imageName":"card-creator-api-prod"},{"containerImage":"frontend","tag":"ziegler-cards-frontend","imageName":"card-creator-frontend-prod"},{"containerImage":"server","tag":"ziegler-cards-server","imageName":"card-creator-server-prod"}]'
          service: ziegler-cards-creator
          cluster: ziegler-cards-cluster
          build-command: docker/docker-compose.prod.yml
          aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
          aws-secret-access-key: ${{ secrets.AWS_ACCESS_KEY }}
          aws-region: eu-central-1
          ecr: 049470867734.dkr.ecr.eu-central-1.amazonaws.com
```
