## 🔍 Connectivity Verification

### Public Instance Internet Access Test

# Connect to public instance via EC2 Instance Connect
sudo su
yum -y update  # Should succeed (proof of internet access via IGW)

### Private Instance Isolation Test

# Transfer key to public instance for SSH access to private subnet
vi MyKey.pem          # Paste your private key content
chmod 400 MyKey.pem   # Secure key permissions

# SSH into private instance
ssh -i "MyKey.pem" ec2-user@<PRIVATE_IP>

# Verify no internet access
sudo su
yum -y update  # Should fail (expected - no direct internet access)

### NAT Gateway Verification (Later Test)
# After NAT Gateway setup, retest in private instance:
sudo su
yum -y update  # Should now succeed (via NAT Gateway)



   ```markdown
   ## 🛠️ CLI Commands
   All AWS CLI commands used are documented in [commands.md](commands.md).
