@Library('utils@master') _
import com.lmig.intl.cloud.jenkins.util.EnvConfigUtil


node('linux') {
    def envUtil = new EnvConfigUtil()
    countryParams = envUtil.getCountryEnvDetails(env.JOB_NAME)
    echo "Working in env: ${countryParams.countryEnv}"
    if (countryParams.countryEnv.toLowerCase() == "dev")
    {
        echo "Doing Dev deploy"
        cfnDeploy(file:'intl-latam-ec-cloudfront.yaml', stackName:"${StackName}")
    } else if (countryParams.countryEnv.toLowerCase() == "prod")
    {
        echo "Doing Dev in prod"
        cfnDeploy(file:'intl-latam-ec-cloudfront-prod.yaml', stackName:"${StackName}")
    }
   
    
}
