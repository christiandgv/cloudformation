@Library('utils@master') _
import com.lmig.intl.cloud.jenkins.util.EnvConfigUtil


node('linux') {
    def envUtil = new EnvConfigUtil()
    countryParams = envUtil.getCountryEnvDetails(env.JOB_NAME)
    echo "Working in env: ${countryParams.countryEnv}"
    if (countryParams.countryEnv.toLowerCase() == "dev")
    {
        echo "Doing Dev deploy"
		//cfnDeploy(file:'cloud_complete_params.json', stackName:"${StackName}", BucketName:"${BucketName}", DomainName:"${DomainName}", PriceClass:"${PriceClass}")
		cfnDeploy(file:'io_access.json', stackName:"${StackName}", BucketName:"${TableDemo}")
    }
}
