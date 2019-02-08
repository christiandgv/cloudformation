@Library('utils@master') _
import com.lmig.intl.cloud.jenkins.util.EnvConfigUtil


node('linux') {
    def envUtil = new EnvConfigUtil()
    countryParams = envUtil.getCountryEnvDetails(env.JOB_NAME)
    echo "Working in env: ${countryParams.countryEnv}"
    if (countryParams.countryEnv.toLowerCase() == "dev")
    {
        echo "Doing Dev deploy"
        cfnDeploy(file:'basic-ec2-windows.json', stackName:"${StackName}")
    }
    else
    {
        echo "Doing Prod or NP deploy"
        cfnDeploy(file:'basic-ec2-windows-prod.json', stackName:"${StackName}")
    }
    
}
